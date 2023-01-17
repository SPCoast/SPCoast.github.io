---
iseagle: true
sidebar: spcoast_sidebar
title: cpOD
project: cpOD
designer: John Plocher
author: John Plocher
fabricated: yes
fab_date: 2021.09
status: released
publish: yes
tags: [eagle, MRCS]
layout: eagle
image_path: cpOD.top.brd.png
tagline: cpOD
overview: >
    Pulse Transformer based Occupancy Detector
    
    Inspired by Dr Bruce Chubb's and Keith Wishowski's DCCOD, as well as work done by MFS and MRCS
    
    The cpOD has the same advantages as the DCCOD, implemented with surface mount components that make it much less expensive to manufacture:
      * Transformer based isolarion keeps track power away from logic and control systems
      * Adjustable sensitivity helps tame layout humidity and ballasting changes
      * Fast detection with slow dropout (hysteresis) makes it forgiving of dirty track and wheels
      * LED activates before hysteresis delay
      * Occupancy detection logic level output is open drain, compatible with C/MRI and other layout control systems (max steady state load 100mA @ 48v)
      * Pin compatible with the Dr. Chubb's ODMB and MRCS's ODX4 motherboards
    
    Differences:
      * Uses a 5v-12v DC power supply, draws less than 5mA
      * Handles track currents up to 60A (absolute max), 10A nominal.
      
    
    
---


This technical documentation is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike](https://creativecommons.org/licenses/by-nc-sa/3.0/)
