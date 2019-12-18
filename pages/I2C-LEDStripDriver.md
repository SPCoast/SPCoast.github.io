---
iseagle: true
sidebar: spcoast_sidebar
title: I2C-LEDStripDriver
project: I2C-LEDStripDriver
designer: John Plocher
fabricated: yes
fab_date: 2019-03
image_path: I2C-LEDStripDriver-Graphic.png
status: released
release: yes
tags: [eagle, SPCoast]
layout: eagle
tagline: WiFi/I2C LED Strip Driver based on a PCA9685 
overview: >
    
    The PCA9685 is an I2C-bus controlled 16-channel LED controller optimized for Red/Green/Blue/Amber (RGBA) color backlighting applications.
    Each LED output has its own 12-bit resolution (4096 steps) fixed frequency individual PWM controller
    
    
    This design drives 2x RGB LED strips and 2x "white" strips - one set for backdrop lighting (dawn and dusk sunsets...) and the other for overhead (sunlight) valence illumination.
    
    
    The 2.0 version includes a Wemos D1 8266 as a stand alone controller; I plan for this board to be used as-is with distributed lighting installations around my layout, all responding to the same "broadcast" lighting control channel over MQTT.
    
    The I2C interface can be used to connect a [I2C-AD4DA](/pages/I2C-AD4DA) and [AD4DA-LightUI](/pages/AD4DA-LightUI.html) for manual lighting control and presets.
    
    
images:
  - image_path: /versions/I2C-LEDStripDriver/I2C-LEDStripDriver-Graphic.png
    title: I2C-LEDStripDriver-Graphic
artifacts:
  - path: /versions/I2C-LEDStripDriver/DMN4469LSS-MOSFETdriver-DataSheet.pdf
    tag: DMN4469LSS-MOSFETdriver-DataSheet.pdf
    type: download
    post: Documentation
  - path: /versions/I2C-LEDStripDriver/PCA9685-Datasheet.pdf
    tag: PCA9685-Datasheet.pdf
    type: download
    post: Documentation
---


This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
