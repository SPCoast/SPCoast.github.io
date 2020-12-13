---
iseagle: true
sidebar: spcoast_sidebar
title: ATEM-Tally-SDI
project: ATEM-Tally-SDI
designer: John Plocher
author: John Plocher
fabricated: yes
fab_date: 2020.11
status: released
release: yes
tags: [eagle, SPCoast]
layout: eagle
image_path: ATEM-Tally-SDI.top.brd.png
tagline: Part 1 of a RFM69-based BlackMagic ATEM Tally Light system - ATEM SDI Interface
overview: >
    
      * Part 1 is the [SDI-connected controller](https://www.spcoast.com/pages/ATEM-Tally-SDI.html)
      * Part 2 is the on-[camera tally light display](https://www.spcoast.com/pages/ATEM-Tally-Camera-Light.html)
      * Arduino sketch for both: [ATEM Tally Sketch](https://www.spcoast.com/pages/ATEMTallyLightRadio.html)
    
    The controller uses the BMD SDI-Shield as an I2C interface to the control signals embedded in the SDI video stream emitted by the ATEM switchers, connected to an AdaFruit RadioFeather AVR 32u4 RFM69 controller and an AdaFruit neopixel strip.  
    
    The Tally light receivers use the same AdaFruit RadioFeather RFM68 AVR 32U4 sticks with a NeoPixel strip that displays Red (LIVE), Green (PREVIEW) or dim Blue (operational, but not currently selected).
    
    
    
    
artifacts:
  - path: /versions/ATEM-Tally-SDI/eagle.epf
    tag: eagle
    type: download
    post: 
---


This sketch is licensed under the [MIT License](https://opensource.org/licenses/MIT)
