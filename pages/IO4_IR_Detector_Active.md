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

//#define DEBUG

#define HEADROOM 40
#define HYSTERESIS 2000    // in mS units, 2000 = 2.0 seconds

#define OCCUPIED LOW
#define EMPTY    ~OCCUPIED

#define LIT 0
#define DIM 1


#include <Arduino.h>

class Circuit {
public:
    Circuit(void) {};
              //          IRTX       IRRX      IO4      ledFeedback
    void init(int number, int irout, int irin, int io4, int led) {
        num = number;
        outPin  = irout;
        inPin   = irin;
        io4Pin  = io4;
        ledPin  = led;
        
        detected = false;
        delaytime = 0;
        pinMode(outPin,  OUTPUT);
        pinMode(io4Pin,  OUTPUT);
        pinMode(ledPin,  OUTPUT);
        pinMode(inPin,   INPUT);
        
#ifdef DEBUG
        digitalWrite(io4Pin,LIT); digitalWrite(ledPin,LIT);  delay(100); 
#endif
        digitalWrite(io4Pin,DIM); // Leave the detection pin 
        digitalWrite(ledPin,DIM); // and LED OFF 
    };
    
    int check(void) {
        digitalWrite(outPin, 0);       // turn off IR transmitter
        delay(5);
        int r1 =  analogRead(inPin);   // read ambient light intensity
        
        digitalWrite(outPin, 1);       // turn ON IR source
        delay(5);
        int r2 = analogRead(inPin);    // see if anything is reflecting
        
        digitalWrite(outPin, 0);       // make sure things are turned off when done

        if ((r2 - r1) > HEADROOM) {    // if a major positive difference, something has been detected...
            delaytime = 0;  // expiration timer is reset every time detection is seen
            digitalWrite(ledPin, OCCUPIED); 
            if (detected == false) {   // newly triggered
#ifdef DEBUG
                Serial.print("ON  ");
                Serial.print(num, DEC);
                Serial.print(": ambient=");
                Serial.print(r1, DEC);
                Serial.print(", reflected=");
                Serial.print(r2, DEC);
                Serial.print(", diff=");
                Serial.print(r2-r1, DEC);
#endif
            }
            detected = true;
        } else {
            digitalWrite(ledPin, EMPTY);
        }
        if (detected) {
            if (delaytime < HYSTERESIS) {
                digitalWrite(io4Pin, OCCUPIED); 
            } else {
#ifdef DEBUG
                Serial.print("OFF "); 
                Serial.println(num, DEC);
#endif
                digitalWrite(io4Pin, EMPTY); 
                detected = false;
            }
        }
        return detected ? 1 : 0;
    };
    
private:  
    int num;
    elapsedMillis delaytime;
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

//#define DEBUG // both here and in the Circuit.h file...   for serial debug messages

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

    circuit[0].init(0, 2, A0, 6, 10);
    circuit[1].init(1, 3, A1, 7, 11);
    circuit[2].init(2, 4, A2, 8, 12);
    circuit[3].init(3, 5, A3, 9, 13);
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
 
~~~
