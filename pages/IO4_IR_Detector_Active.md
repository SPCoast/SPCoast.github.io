---
isarduino: true
sidebar: spcoast_sidebar
title: IO4_IR_Detector_Active
project: IO4_IR_Detector_Active
designer: plocher
author: plocher
tags: [arduino, SPCoast]
layout: arduino
tagline: description not provided
overview: >
    
artifacts:
  - path: /sketches/IO4_IR_Detector_Active/Circuit.h
    tag: Circuit.h
    type: download
    post: Arduino Sketch header file
  - path: /sketches/IO4_IR_Detector_Active/IO4_IR_Detector_Active.ino
    tag: IO4_IR_Detector_Active.ino
    type: download
    post: Arduino Sketch
  - path: /sketches/IO4_IR_Detector_Active/sketch.json
    tag: sketch
    type: download
    post: 
---

## Circuit

~~~ cpp
#ifndef _CIRCUIT_
#define _CIRCUIT_

// Abstraction for the IR Detector 
//
// Basic operation:
//   turn IR LED OFF and read ambient IR level
//   turn IR LED ON  and read newly bright IR level
//
//   If there is a reasonable difference, presume detection
//   Keep resetting hysteresis timeout to 0 every time there is detection
//   if no detection for longer than hysteresis, declare block as empty
//
// Onboard feedback LEDS follow real time differences in IR levels to allow tuning
// IO4-feedback follows the detection with hysteresis

#include <elapsedMillis.h>

//#define SHOW_IMMEDIATE

#define HYSTERESIS 2000    // in mS units, 2000 = 2.0 seconds

#define OCCUPIED LOW
#define EMPTY    ~OCCUPIED

#define LIT 0
#define DIM 1
#define SAMPLES 30
#define DWELL 4

#include <Arduino.h>

class Circuit {
private:
    enum State { R1, R2 };
public:
    Circuit(void) {};
              //          IRTX       IRRX      IO4      headroom, ledFeedback
    void init(int number, int irout, int irin, int io4, int head, int led = -1) {
        num = number;
        outPin  = irout;
        inPin   = irin;
        io4Pin  = io4;
        ledPin  = led;
        headroom = head;

        state = R1;
        sample  = 0;
        for (int x = 0; x < SAMPLES; x++) {
            r1[x] = r2[x] = 0;
        }
        
        detected = false;
        delaytime = 0;
        dwelltime = 0;
        pinMode(outPin,  OUTPUT);
        pinMode(io4Pin,  OUTPUT);
        pinMode(inPin,   INPUT);
        if (ledPin != -1) { 
            pinMode(ledPin,  OUTPUT);
            digitalWrite(ledPin,DIM); // and LED OFF 
        }
        digitalWrite(io4Pin,DIM); // default the detection pin to EMPTY
    };
    
    int check(void) {
        if (dwelltime > DWELL)  { // state machine ticks in increments of DWELLTIME...
            dwelltime = 0;
            
            switch (state) {
                case R1:    r1[sample] =  analogRead(inPin);
                            digitalWrite(outPin, 1);       // turn ON IR source
                            state = R2;
                            break;
                            
                case R2:    r2[sample] =  analogRead(inPin);
                            digitalWrite(outPin, 0);       // make sure things are turned off when done


                            // calculate the runnuing average difference
                            long int t1 = 0, t2 = 0;
                            for (int x = 0; x < SAMPLES; x++) {
                                t1 += r1[x];
                                t2 += r2[x];
                            }
                            t1 /= SAMPLES;
                            t2 /= SAMPLES;


                            // Visual Feedback LED
                            if (ledPin != -1) {   // real time feedback on a per-reading basis...
                                int v1, v2;
#ifdef SHOW_IMMEDIATE
                                v1 = r1[sample];
                                v2 = r2[sample];
#else
                                v1 = t1;
                                v2 = t2;
#endif
                                if ((v2 - v1) >= headroom) {
                                      digitalWrite(ledPin, OCCUPIED);
#ifdef DEBUG
                                      if (num == DEBUG) {
                                        Serial.print("a=");
                                        Serial.print(v1, DEC);
                                        Serial.print(", r=");
                                        Serial.print(v2, DEC);
                                        Serial.print(", diff=");
                                        Serial.println(v2-v1, DEC);
                                      }
#endif
                                } else {
                                    digitalWrite(ledPin, EMPTY);
                                }
                            }

                            // IO4 Feedback signal - always smoothed version and add hysteresis
                            if ((t2 - t1) > headroom) {    // if different, something has been detected...
                                delaytime = 0;  // expiration timer is reset every time detection is seen

#ifdef DEBUG
                                if (detected == false) {   // newly triggered
                                    if (num == DEBUG) {
                                      Serial.print("ON  ");
                                      Serial.print(num, DEC);
                                      Serial.print(": ambient=");
                                      Serial.print(t1, DEC);
                                      Serial.print(", reflected=");
                                      Serial.print(t2, DEC);
                                      Serial.print(", diff=");
                                      Serial.print(t2-t1, DEC);
                                  }                         
                              }
#endif   
                              detected = true;
                          }
                          
                          if (detected) {
                              if (delaytime < HYSTERESIS) {
                                  digitalWrite(io4Pin, OCCUPIED); 
                              } else {  // no detection seen for a while...
                                  digitalWrite(io4Pin, EMPTY); 
                                  detected = false;
#ifdef DEBUG
                                  if (num == 0) {
                                      Serial.print("OFF "); 
                                      Serial.println(num, DEC);
                                  }
#endif
                              }
                          }
                          state = R1;
                          sample++;
                          if (sample >= SAMPLES) sample = 0;
                          break;    
            }
        }
        return detected ? 1 : 0;
    };
    
private:  
    int num;
    elapsedMillis delaytime;
    State state;
    elapsedMillis dwelltime;
    int r1[SAMPLES];
    int r2[SAMPLES];
    int headroom;
    byte sample;
    int detected;
    int outPin;
    int inPin;
    int ledPin;
    int io4Pin;
};

#endif
 
~~~

## IO4_IR_Detector_Active

~~~ cpp
//DESC:Arduino based proximity sensor
//BOARD:IO4-IR-Detector-Active
//AUTHOR:John Plocher
//LICENSE:MIT License
//
//   Based very loosely on work done by Dustin Andrews 2012
//  
//   Copyright (c) 2014, 2020 John Plocher, released under the terms of the MIT License (MIT)
//
 
#include <elapsedMillis.h>
// #define V21A      // older board version based on Duemilanove Mega-128

//#define DEBUG 2 // both here and in the Circuit.h file...   for serial debug messages

elapsedMillis t1;

#define ACTIVITY_LED 18

#define BLINKTIME 2000

#include "Circuit.h"

Circuit circuit[4];

void setup() 
{       
#ifdef DEBUG
    // Configure the serial port
    Serial.begin(115200);
    Serial.println("IR Detector");  
    t1 = 0; 
#endif
    analogReference(DEFAULT);
    pinMode(ACTIVITY_LED, OUTPUT);
    pinMode(A0, INPUT);
    pinMode(A1, INPUT);
    pinMode(A2, INPUT);
    pinMode(A3, INPUT);

    //              IRTX,IRRX,IO4, headroom, ledFeedback

#ifdef V21A // has no independent LED feedback...
    circuit[0].init(0, 2, A0, 6, 15);
    circuit[1].init(1, 3, A1, 7, 15);
    circuit[2].init(2, 4, A2, 8, 15);
    circuit[3].init(3, 5, A3, 9, 15);
#else
    //  The headroom parameter compensates for sensor differences and fluorescent light interference
    circuit[0].init(0, 2, A0, 6, 50, 10);
    circuit[1].init(1, 3, A1, 7, 90, 11);
    circuit[2].init(2, 4, A2, 8, 20, 12);
    circuit[3].init(3, 5, A3, 9, 20, 13);
#endif
}

bool activity = 0;

void loop() 
{
    if (t1 > BLINKTIME) { 
        activity = !activity;
        digitalWrite(ACTIVITY_LED, activity);
        if (activity) t1 = 0; else t1 = BLINKTIME - 1; // long off, short ON...
    }
    for (int x = 0; x < 4; x++) {
        circuit[x].check();
    }
}

#define ITEMS 30
int r1[ITEMS];
int r2[ITEMS];
long int av1, av2;
int item = 0;

// DELAY = 4: 1:8 (7)  for old style sensor

void xxloop() {
#define IRLED 3
#define IRRX  A1
#define DELAY 4
  digitalWrite(IRLED, 0); delay(DELAY); int v1 =  analogRead(IRRX);        // IR is off
  digitalWrite(IRLED, 1); delay(DELAY); int v2 =  analogRead(IRRX);        // IR is on

  r1[item] = v1;
  r2[item] = v2;
  av1 = av2 = 0;
  for (int x = 0; x < ITEMS; x++) {
    av1 += r1[x];
    av2 += r2[x];
  }
  av1 /= ITEMS;
  av2 /= ITEMS;

  item++;
  if (item >= ITEMS) item = 0;
  
  Serial.print(av1); Serial.print(' ');
  Serial.print(av2); Serial.print(' ');
  Serial.print(av2-av1); Serial.println();

}
 
~~~
