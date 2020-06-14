---
iseagle: true
sidebar: spcoast_sidebar
title: IOB-Turtle
project: IOB-Turtle
designer: John Plocher
fabricated: yes
fab_date: 2018-02
status: released
release: yes
tags: [eagle, SPCoast, IOB, Adapter]
image_path: IOB-Turtle-Graphic.png
layout: eagle
tagline: IOB Interface provides 1x IO4 port for connection to an IO4-Turtle
overview: >
    
      * V2.0:  new IOB layout
    
images:
  - image_path: /versions/IOB-Turtle/IOB-Turtle-Graphic.png
    title: IOB-Turtle-Graphic
artifacts:
  - path: /versions/IOB-Turtle/IOB-Turtle_array.scr
    tag: IOB-Turtle_array.scr
    type: download
    post: Eagle SCRipt
  - path: /versions/IOB-Turtle/PanelTemplate.brd
    tag: PanelTemplate.brd
    type: download
    post: Eagle PCB file
---

## Documentation

PNP Ready: IOB-Turtle - adapter for [IO4-Turtle](/pages/IO4-Turtle) controller and [I2C-7311](/pages/I2C-7311) IO expansion board

  * pin 1: 9-12vDC
  * pin 2: !DIVERGING - Turnout Position Feedback - low = Diverging, high = not diverging
  * pin 3: !NORMAL    - Turnout Position Feedback - low = Normal, high = not normal
  * pin 4: !OCCUPIED  - Detector - low = occupied, high = empty
  * pin 5: !MOTOR     - Motor Control Output - Low = Normal, High = Diverging
  * pin 6: GND


## doc

PNP Ready: IOB-Turtle - adapter for [IO4-Turtle](/pages/IO4-Turtle) controller and [I2C-7311](/pages/I2C-7311) IO expansion board

  * pin 1: 9-12vDC
  * pin 2: !DIVERGING - Turnout Position Feedback - low = Diverging, high = not diverging
  * pin 3: !NORMAL    - Turnout Position Feedback - low = Normal, high = not normal
  * pin 4: !OCCUPIED  - Detector - low = occupied, high = empty
  * pin 5: !MOTOR     - Motor Control Output - Low = Normal, High = Diverging
  * pin 6: GND



This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
