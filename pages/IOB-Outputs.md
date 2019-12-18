---
iseagle: true
sidebar: spcoast_sidebar
title: IOB-Outputs
project: IOB-Outputs
designer: John Plocher
fabricated: no
fab_date: 
status: released
release: yes
tags: [eagle, SPCoast]
image_path: IOB-Outputs-Graphic.png
layout: eagle
tagline: IOB Interface provides 1x IO4 port with 4x open drain output i/o lines.
overview: >
    
    Changes: Output only - non-inverting Open Drain current sink
    
images:
  - image_path: /versions/IOB-Outputs/IOB-Outputs-Graphic.png
    title: IOB-Outputs-Graphic
artifacts:
  - path: /versions/IOB-Outputs/IOB-Outputs.b#1
    tag: IOB-Outputs
    type: download
    post: 
  - path: /versions/IOB-Outputs/IOB-Outputs_array.scr
    tag: IOB-Outputs_array.scr
    type: download
    post: Eagle SCRipt
  - path: /versions/IOB-Outputs/PanelTemplate.brd
    tag: PanelTemplate.brd
    type: download
    post: Eagle PCB file
---

## Documentation

## IOB-Outputs


PNP Ready: Panelized IOB quad "output board", used for driving LEDS and other devices from the [I2C-7311](/pages/I2C-7311) IO expansion board

Features:

* 5v or 9-12v supply,
* Open Drain outputs
* pins are active low

IO4:

* pin 1: 5vDC
* pin 2: !OUT1
* pin 3: !OUT2
* pin 4: !OUT3
* pin 5: !OUT4
* pin 6: GND




## doc

## IOB-Outputs


PNP Ready: Panelized IOB quad "output board", used for driving LEDS and other devices from the [I2C-7311](/pages/I2C-7311) IO expansion board

Features:

* 5v or 9-12v supply,
* Open Drain outputs
* pins are active low

IO4:

* pin 1: 5vDC
* pin 2: !OUT1
* pin 3: !OUT2
* pin 4: !OUT3
* pin 5: !OUT4
* pin 6: GND





This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
