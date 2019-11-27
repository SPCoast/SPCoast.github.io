---
iseagle: true
sidebar: spcoast_sidebar
title: Core-ESP32
project: Core-ESP32
designer: John Plocher
fabricated: yes
fab_date: 2019-03
status: released
release: yes
layout: eagle
tags: [SPCoast, eagle]
tagline: Core Field Unit Processor board using an ESP32 Dev Board with Wifi, BLE and a small OLED screen
overview: >
    
    A platform to prove out the ESP32 environment (maybe with circuit python) as a field unit implementation platform,
    allowing the software stack to be generalized and possibly based off of interpreted text file based data structures rather than customized C++ code.
    
    
    Geekcreit ESP32 WROOM
    
      * Converted J6 - the Codeline RJ12 - to full IO4 (with 0.100 alternate...) since the [I2C-Codeline-Matrix](/pages/I2C-Codeline-Matrix) is now operational
      * Beefed up VIN traces to support higher prolonged current draws
    
images:
  - image_path: /versions/Core-ESP32/DOIT-ESP32-Dev.png
    title: DOIT-ESP32-Dev
  - image_path: /versions/Core-ESP32/ESP32-OLED-pinout.jpg
    title: ESP32-OLED-pinout
  - image_path: /versions/Core-ESP32/Core-ESP32-Graphic.png
    title: Core-ESP32-Graphic
artifacts:
  - path: /versions/Core-ESP32/ESP32-DevKitJ-v1_sch.pdf
    tag: ESP32-DevKitJ-v1_sch.pdf
    type: download
    post: Documentation
---


This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
