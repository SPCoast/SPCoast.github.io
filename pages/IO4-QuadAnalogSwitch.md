---
iseagle: true
sidebar: spcoast_sidebar
title: IO4-QuadAnalogSwitch
project: IO4-QuadAnalogSwitch
designer: John Plocher
author: John Plocher
fabricated: yes
fab_date: 2021.06
status: experimental
publish: yes
tags: [eagle, SPCoast]
layout: eagle
image_path: IO4-QuadAnalogSwitch.top.brd.png
tagline: Quad Analog switch - 16 inputs to 4 A/D lines
overview: >
    
    An ESP32 only has 4x usable A/D lines when WiFi is also used.
    This board is a multiplexor for 4 banks of 4 analog inputs to those A/D lines.
    
    The initial use case is to support a preset controller for LED layout lighting
    that has R,G,B and W levels for Background horizon, background sky, foreground sky and suplementary lighting.
    (that is, 4 banks of 4 linear potentiometers each...)
    
    Usage:
    
    Set the digital outputs to select the desired bank:
        D C B A
        X 0 1 1	Bank A
        X 0 0 1	Bank B
        X 1 0 0	Bank C
        X 0 0 0	Bank D
    
    (output "D" controls a diagnostic LED on the board)
    
artifacts:
  - path: /versions/IO4-QuadAnalogSwitch/IO4-QuadAnalogSwitch copy.brd
    tag: IO4-QuadAnalogSwitch copy.brd
    type: download
    post: Eagle PCB board file
  - path: /versions/IO4-QuadAnalogSwitch/IO4-QuadAnalogSwitch-fake.brd
    tag: IO4-QuadAnalogSwitch-fake.brd
    type: download
    post: Eagle PCB board file
  - path: /versions/IO4-QuadAnalogSwitch/eagle.epf
    tag: eagle
    type: download
    post: 
---


This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
