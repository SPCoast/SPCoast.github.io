---
iseagle: true
sidebar: spcoast_sidebar
title: IO4-SignalDriver-Small
project: IO4-SignalDriver-Small
designer: John Plocher
image_path: IO4-SignalDriver-Small-Graphic.png
author: John Plocher
fabricated: yes
fab_date: 2019.09
status: released
release: yes
tags: [eagle, SPCoast]
layout: eagle
tagline: IO4 Output adapter driver for a 2-head signal mast
overview: >
    
    Takes an IO4-Output and drives 2x 3-LED common Anode signal heads using a demultiplexor logic chip.
    
    Designed in conjunction with Jay Beckham for his South Shore Lines layout
    
    Circuit info:
      * The board is driven from an IO4 port that carries +5, GND and 4x output signals.
      * Signal heads / LEDs are "common anode" - pin4 of the signal head connector is VCC, the "colors" pins are driven LOW to energize the LED.
      * The board can drive 2x signal heads, each with R, Y, G and DARK aspects
          * Control signals 1 & 2 and  3 & 4, each control one head:
              : 00 - Green
              : 01 - Yellow
              : 10 - Red
              : 11 - Dark
      * This board does not have provision for adjustable LED brightness.  The resistors are fixed at production time for high efficiency LEDS used in SPCoast's Simple Signal masts.
    
images:
  - image_path: /versions/IO4-SignalDriver-Small/IO4-SignalDriver-Small-Graphic.png
    title: IO4-SignalDriver-Small-Graphic
artifacts:
  - path: /versions/IO4-SignalDriver-Small/IO4-SignalDriver-Small_array.scr
    tag: IO4-SignalDriver-Small_array.scr
    type: download
    post: Eagle SCRipt
---


This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
