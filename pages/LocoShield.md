---
iseagle: true
sidebar: spcoast_sidebar
title: LocoShield
project: LocoShield
designer: John Plocher
fabricated: yes
fab_date: 2022-03
status: released
release: yes
image_path: LocoShield-Graphic.png
tags: [eagle, SPCoast, LCB, Adapter]
layout: eagle
tagline: An electrical interface to Digitrax Loconet
overview: >
    
    LocoShield Protoboard - SMT
    
    V2.0 Removes "shield" form factor, as many are using other procesor styles
    
    This version supports active bus termination.  Only one device on the LNet needs to supply termination.
    
    Wiring:
      * Ground
      * TXdata
      * RXdata
      * 5vDC
      * (if active termination is used) +12vDC
    
images:
  - image_path: /versions/LocoShield/Assembled-14-2.jpg
    title: Assembled-14-2
  - image_path: /versions/LocoShield/Assembled-14-1.jpg
    title: Assembled-14-1
  - image_path: /versions/LocoShield/Assembled-12-3.jpg
    title: Assembled-12-3
  - image_path: /versions/LocoShield/Assembled-12-2.jpg
    title: Assembled-12-2
  - image_path: /versions/LocoShield/Assembled-12-1.jpg
    title: Assembled-12-1
  - image_path: /versions/LocoShield/Arduino-LoconetRX1.jpg
    title: Arduino-LoconetRX1
  - image_path: /versions/LocoShield/Arduino-LoconetRX2.jpg
    title: Arduino-LoconetRX2
  - image_path: /versions/LocoShield/Arduino-LoconetRXScope.jpg
    title: Arduino-LoconetRXScope
  - image_path: /versions/LocoShield/Assembled-12-Bottom.jpg
    title: Assembled-12-Bottom
  - image_path: /versions/LocoShield/LocoShieldv13B.jpg
    title: LocoShieldv13B
  - image_path: /versions/LocoShield/Assembled-00-1.jpg
    title: Assembled-00-1
  - image_path: /versions/LocoShield/LocoShield-Graphic.png
    title: LocoShield-Graphic
artifacts:
  - path: /versions/LocoShield/LocoShield-BOM.csv
    tag: LocoShield-BOM
    type: download
    post: 
  - path: /versions/LocoShield/LocoShield-JLC-BOM.csv
    tag: LocoShield-JLC-BOM
    type: download
    post: 
  - path: /versions/LocoShield/LocoShield-JLC-BOM.numbers
    tag: LocoShield-JLC-BOM
    type: download
    post: 
  - path: /versions/LocoShield/LocoShield.CPL.csv
    tag: LocoShield.CPL
    type: download
    post: 
  - path: /versions/LocoShield/LocoShield.SMD-parts.csv
    tag: LocoShield.SMD-parts
    type: download
    post: 
  - path: /versions/LocoShield/LocoShield.parts.numbers
    tag: LocoShield.parts
    type: download
    post: 
  - path: /versions/LocoShield/LocoShield.pdf
    tag: LocoShield.pdf
    type: download
    post: Documentation
  - path: /versions/LocoShield/LocoShield_array-JLC-CPL.csv
    tag: LocoShield_array-JLC-CPL
    type: download
    post: 
  - path: /versions/LocoShield/LocoShield_array-JLC-CPL.numbers
    tag: LocoShield_array-JLC-CPL
    type: download
    post: 
  - path: /versions/LocoShield/LocoShield_array.JLC-BOM.csv
    tag: LocoShield_array.JLC-BOM
    type: download
    post: 
  - path: /versions/LocoShield/LocoShield_array.SMD-partlist.csv
    tag: LocoShield_array.SMD-partlist
    type: download
    post: 
  - path: /versions/LocoShield/LocoShield_array.SMD-parts.csv
    tag: LocoShield_array.SMD-parts
    type: download
    post: 
  - path: /versions/LocoShield/LocoShield_array.scr
    tag: LocoShield_array.scr
    type: download
    post: Eagle SCRipt
  - path: /versions/LocoShield/LocoShield~snap.scr
    tag: LocoShield~snap.scr
    type: download
    post: Eagle SCRipt
  - path: /versions/LocoShield/gerb274x.cam
    tag: gerb274x
    type: download
    post: 
---

## ArduinoLibrary


The EmbeddedLoconet software for this board can be downloaded from [Alex Shepherd](https://github.com/mrrwa/LocoNet)

It is also available in the Arduino IDE via the Library Manager



This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
