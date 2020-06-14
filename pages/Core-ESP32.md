---
iseagle: true
sidebar: spcoast_sidebar
title: Core-ESP32
project: Core-ESP32
designer: John Plocher
author: John Plocher
fabricated: yes
fab_date: 2019-03
fab_date: 
status: released
release: yes
tags: [eagle, SPCoast, Processor]
image_path: Core-ESP32-Graphic.png
layout: eagle
tagline: Core Field Unit Processor board using an ESP32 Dev Board with Wifi, BLE and a small OLED screen
overview: >
    
    A platform to prove out the ESP32 environment (maybe with circuit python) as a field unit implementation platform,
    allowing the software stack to be generalized and possibly based off of interpreted text file based data structures rather than customized C++ code.
    
      * Uses the [30-pin (2x15) "DEV" package](https://www.ebay.com/itm/313026496469)
      * Includes [C/MRI RS485 interface card](https://spcoast.github.io/pages/CMRI-Bus-Interface.html) IO connection
      * Supports I2C OLED: 1306 based 128x32, 128x64...
    
images:
  - image_path: /versions/Core-ESP32/DOIT-ESP32-Dev.png
    title: DOIT-ESP32-Dev
  - image_path: /versions/Core-ESP32/ESP32-OLED-pinout.jpg
    title: ESP32-OLED-pinout
  - image_path: /versions/Core-ESP32/Core-ESP32-Graphic.png
    title: Core-ESP32-Graphic
artifacts:
  - path: /versions/Core-ESP32/Core-ESP32.s##
    tag: Core-ESP32
    type: download
    post: 
  - path: /versions/Core-ESP32/ESP32-DevKitJ-v1_sch.pdf
    tag: ESP32-DevKitJ-v1_sch.pdf
    type: download
    post: Documentation
---


This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
