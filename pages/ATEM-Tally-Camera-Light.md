---
iseagle: true
sidebar: spcoast_sidebar
title: ATEM-Tally-Camera-Light
project: ATEM-Tally-Camera-Light
designer: John Plocher
author: John Plocher
fabricated: yes
fab_date:  2020.11
status: released
release: yes
tags: [eagle, SPCoast]
layout: eagle
image_path: ATEM-Tally-Camera-Light.top.brd.png
tagline: Part 2 of a RFM69-based BlackMagic ATEM Tally Light system - On Camera Light
overview: >
    
    Part 1 is the SDI-connected controller
    Part 2 is the on-camera tally light display
    
    The controller uses the BMD SDI-Shield as an I2C interface to the control signals embedded in the SDI video stream emitted by the ATEM switchers, connected to an AdaFruit RadioFeather AVR 32u4 RFM69 controller and an AdaFruit neopixel strip.  
    
    The Tally light receivers use the same AdaFruit RadioFeather RFM68 AVR 32U4 sticks with a NeoPixel strip that displays Red (LIVE), Green (PREVIEW) or dim Blue (operational, but not currently selected).
    
    The Arduino IDE sketch is available on GitHub (... TBD URL ...)
    
    
    
artifacts:
  - path: /versions/ATEM-Tally-Camera-Light/eagle.epf
    tag: eagle
    type: download
    post: 
---


This sketch is licensed under the [MIT License](https://opensource.org/licenses/MIT)
