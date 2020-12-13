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
    
    
    
images:
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0174.png
    title: IMG_0174
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0175.png
    title: IMG_0175
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0177.png
    title: IMG_0177
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0176.png
    title: IMG_0176
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0172.png
    title: IMG_0172
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0173.png
    title: IMG_0173
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0171.png
    title: IMG_0171
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0170.png
    title: IMG_0170
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0169.png
    title: IMG_0169
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0168.png
    title: IMG_0168
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0181.png
    title: IMG_0181
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0180.png
    title: IMG_0180
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0184.png
    title: IMG_0184
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0178.png
    title: IMG_0178
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0193.png
    title: IMG_0193
  - image_path: /versions/ATEM-Tally-Camera-Light/IMG_0179.png
    title: IMG_0179
artifacts:
  - path: /versions/ATEM-Tally-Camera-Light/IMG_0190.mov
    tag: IMG_0190
    type: download
    post: 
  - path: /versions/ATEM-Tally-Camera-Light/IMG_0191.mov
    tag: IMG_0191
    type: download
    post: 
  - path: /versions/ATEM-Tally-Camera-Light/IMG_0192.mov
    tag: IMG_0192
    type: download
    post: 
  - path: /versions/ATEM-Tally-Camera-Light/eagle.epf
    tag: eagle
    type: download
    post: 
---


This sketch is licensed under the [MIT License](https://opensource.org/licenses/MIT)
