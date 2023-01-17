---
iseagle: true
sidebar: spcoast_sidebar
title: I2C-SignalTestJig
project: I2C-SignalTestJig
designer: John Plocher
author: John Plocher
fabricated: yes
fab_date: 2020.04
status: released
publish: yes
tags: [eagle, SPCoast, Signal, I2C, TestJig]
layout: eagle
image_path: I2C-SignalTestJig.top.brd.png
tagline: Test Jig for simple signal panels
overview: >
    
    An I2C slave board that drives 6x signal head drivers (effectively 3x IOB-Signal circuits)
    in a form factor that mimics the panelization spacing of the simple signal boards.
    
    This allows bulk testing after fabrication of an entire board in 2 (or 4) operations 
      * align a board with the pogo pins
      * press down on pins
      * observe the correct operation of the heads
         * mark any defective units
      * move panel to next set of contacts & repeat
artifacts:
  - path: /versions/I2C-SignalTestJig/PogoPins.jpeg
    tag: PogoPins
    type: download
    post: 
  - path: /versions/I2C-SignalTestJig/TestAssembly.jpeg
    tag: TestAssembly
    type: download
    post: 
---


This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
