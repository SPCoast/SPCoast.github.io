---
iseagle: true
sidebar: spcoast_sidebar
title: IO4-IR-Detector-GBunza
project: IO4-IR-Detector-GBunza
designer: John Plocher
fabricated: yes
fab_date: 2018-02
status: released
release: yes
tags: [eagle, SPCoast]
layout: eagle
tagline: IO4 Quad Optical/IR Detector baseboard
overview: >
    
    Derived from Geoff Bunza's SMA Detector, published in his column in MRH as "SMA23 – A New DCC & DC Car & Loco Detector – Differential Absolute Position Detector (DAPD)"
    
    This version eschews "small" in favor of a remote mountable IO4 baseboard that can be mounted near the point of use, and then use [sensors disguised as ties](/pages/IO4-IR-Detector-GBunza-Fingers.html) for the sensor electronics themselves.
    
    
    It has 4 independent optical detectors for high density applications.  4 Circuit Enhanced Optical Position Detector uses an Arduino ProMini (included) for its timing and de-bounce, so these parameters can be changed in software.
    
    
    The output is an open drain (2N7002) which can sink up to 115mA @ up to 48V.
    
    
    This design uses Geoff's self-calibrating detection circuit, so you
    don't need to adjust for ambient light level.  Note the circuit
    won't work in the dark unless you provide an infrared illumination
    source.  The supply voltage range is 5 volts and the the output is
    an open drain (2N7002) which can sink up to 100mA @ 48V.
    
    
    Geoff says:
    
      >  "Every so often one needs an absolute position detector, rather
      > than a block detector. The best I’ve used employ their own light
      > source, but older designs use Cadmium Sulphide (CdS) photocells
      > and depend on ambient light in the room. Both have driven me crazy
      > with their limitations. This article describes a new design, using
      > ambient light “seen” by the detector in two places – typically
      > between the rails and just to the side of the track. When it
      > notices the track light level fall below the level of the second
      > sensor, it “indicates” the presence of an obstruction (car or
      > loco). The beauty of this “differential” measurement is that it
      > operates over a very wide range of light levels, does not require
      > “aiming” to a target, needs no adjustments, and can be virtually
      > buried in ground covering materials."
    
    
images:
  - image_path: /versions/IO4-IR-Detector-GBunza/IR-Detector-GBunza-Graphic.png
    title: IR-Detector-GBunza-Graphic
artifacts:
  - path: /versions/IO4-IR-Detector-GBunza/IRDetector-Gbunza.ino
    tag: IRDetector-Gbunza.ino
    type: download
    post: Arduino Sketch
  - path: /versions/IO4-IR-Detector-GBunza/PT19-21C-L41-TR8-Phototransistor.pdf
    tag: PT19-21C-L41-TR8-Phototransistor.pdf
    type: download
    post: Documentation
  - path: /versions/IO4-IR-Detector-GBunza/tl331-Comparator.pdf
    tag: tl331-Comparator.pdf
    type: download
    post: Documentation
---

## IRDetector-Gbunza.ino

~~~ cpp
#define DET1  2
#define DET2  3
#define DET3  4
#define DET4  5
#define OUT1  6
#define OUT2  7
#define OUT3  8
#define OUT4  9
#define LED1  13
#define LED2  12
#define LED3  11
#define LED4  10

#define HYSTERESIS (long)2000    // in mS units, 2000 = 2.0 seconds

#define OCCUPIED LOW
#define EMPTY    ~OCCUPIED


#define smillis() ((long)millis())

class Detector {
public:
    Detector(int number, int det, int out, int led) {
      init(number, det, out, led);
    }
    
    Detector(void) {
        num       = -1;
        detPin    = -1;
        outPin    = -1;
        ledPin    = -1;
        delaytime = smillis();
        detected  = false;
    }
    
    void init(int number, int det, int out, int led) {
        num       = number;  // 1..4
        detPin    = det;
        outPin    = out;
        ledPin    = led;
        detected  = false;   // default to unoccupied...
        delaytime = smillis();  // expired...
        pinMode(ledPin,     OUTPUT);
        pinMode(outPin,     OUTPUT);
        pinMode(detPin,     INPUT);
        digitalWrite(outPin, detected ? OCCUPIED : EMPTY); 
        digitalWrite(ledPin, detected ? LOW : HIGH); 
    }
    
    boolean after(long timeout) {
        return smillis()-timeout>0;
    }

    boolean check(void) {
        if (num == -1) return false;
      
        int r1 =  digitalRead(detPin);
        if (r1 == HIGH) {
            detected = true;
            delaytime = smillis() + HYSTERESIS;  // expiration time is pushed out every time detection is seen
        }
        // hysteresis expired without further detection events
        if (after(delaytime)) {
            detected = false;
        }
        // report occupancy...
        digitalWrite(outPin, detected ? OCCUPIED : EMPTY); 
        digitalWrite(ledPin, detected ? LOW : HIGH); 
        return detected;
    }
    
private:  
    int      num;
    long     delaytime;
    boolean  detected;
    int      detPin;
    int      outPin;
    int      ledPin;
};


Detector circuit0(0, DET1, OUT1, LED1);
Detector circuit1(1, DET2, OUT2, LED2);
Detector circuit2(2, DET3, OUT3, LED3);
Detector circuit3(3, DET4, OUT4, LED4);

void setup() {
}

void loop() {
    circuit0.check();
    circuit1.check();
    circuit2.check();
    circuit3.check();
}
~~~




This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
