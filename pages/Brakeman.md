---
iseagle: true
sidebar: spcoast_sidebar
title: Brakeman
project: Brakeman
designer: John Plocher
fabricated: yes
fab_date: 2016.11
image_path: Lit.jpg
status: released
publish: yes
tags: [eagle, SPCoast, Misc]
layout: eagle
tagline: An electronic DCC-track-driven figurine with a red or blue LED
overview: >
    
    For best results when fabricating, choose
      * ENIG (gold) rather than a Hot Air Solder Layer (HASL) for the pads
      * White or Blue soldermask
      * Panalize = 2x designs
    
    
    
images:
  - image_path: /versions/Brakeman/Unlit.jpg
    title: Unlit
  - image_path: /versions/Brakeman/Mockup.jpg
    title: Mockup
  - image_path: /versions/Brakeman/Fabricated.jpg
    title: Fabricated
  - image_path: /versions/Brakeman/Packaged.jpg
    title: Packaged
  - image_path: /versions/Brakeman/Assembled.jpg
    title: Assembled
  - image_path: /versions/Brakeman/Lit.jpg
    title: Lit
  - image_path: /versions/Brakeman/Fabricated-backside.jpg
    title: Fabricated-backside
---

## GCOR

## GCOR Rule 6.19 D (paraphrased)

> When a train stops on a main track, flag protection must be provided


On a layout, torpedoes and fusees are a bit over the top, but a
brakeman/flagman with a red lantern can add a twist to your next operating
session.  Adopt prototype practices and have your crews protect
their trains when switching a town or otherwise fouling the main.
Just don't forget to recall the flagman before leaving town!


## Designed in the NMRA/PCR for DCC layouts

Assembly required
 
1. V1.0-1.3: Use a track nipper to detach the base from the hand holding the LED.
1. V2.x: Snap the base from the feet and remove any extra PCB frame from around the figure.
1. Solder the two feet to the two small gold pads on the top of the base
1. You can solder a wire (the clipped off resistor leads work well) to strengthen and align this connection
1. Attach the weight to the top of the base next to (but not touching) his feet with double sided foam tape
1. Place the large gold pads across the rails to light the red lantern.

Variation:
  * Make a "Safety Sam" to indicate track or rolling stock that must not be used/moved.  Use 2 BLUE LEDs instead of one RED one - solder them "back to back, opposite" so that one LED's long lead is soldered to the "front" on the raised hand, while the other's long lead is soldered to the figure's "back" on the lowered hand.  Using 2x Blue LEDS is necessary because the Blue LED's have a reverse breakdown voltage close to 5v, while the common Red ones seem to be able to handle 20v+.  (DCC track voltage is ~15v...)

Clean track works best.  Use violates UP Safety Rule 81.2.1, Step Over Rail 

John Plocher, SPCoast.com

> WARNING: This product may contain chemicals known to the State of California to cause cancer and birth defects or other reproductive harm. 


## TestPlan

## Brakeman Testplan and Assembly:

-   SMT 1K0 0805 or PTH resistor on body top surface
-   Cut the LED leads to between 3mm and 4mm long
-   Edge mount the Red LED to the raised arm, polarity does not matter
    -   Colors other than red: must use 2x LEDS, one on each arm, with
        opposite polarity

Testing:

-   Red LED:
    -   Touch 9-12vAC to one \"foot\" and Gnd to the other,
    -   observe RED LED on hand light up.
-   Other Colors:
    -   Touch 9-12vDC to one foot and GND the other,
    -   Observe ONE LED light up
    -   Reverse the foot connections
    -   Observe the OTHER LED light up

The end user will snap apart the base and body, solder the feet to the
base and attach a lead weight to the base, making a figure with a LED
lantern in its hand that lights up when placed on a HO model railroad
track.



This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
