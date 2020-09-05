---
iseagle: true
sidebar: spcoast_sidebar
title: IOB-Baseboard
project: IOB-Baseboard
designer: John Plocher
author: John Plocher
fabricated: no
fab_date: 
status: released
release: yes
tags: [eagle, SPCoast]
layout: eagle
image_path: 1.0/IOB-Baseboard-1.0.top.brd.png
tagline: IOB Baseboard - wiring termination and I2C / Power bus management
overview: >
    
    The latest in the evolution of the perfect layout I/O system...
    Previous I2C-xxx designs either let to a proliferation of adapters
    (current sink, input filters...) and to less than robust mechanical
    designs (daughtercards that easily pulled out of their sockets with
    cable movement)
    
    This version does 4 things:
     * All wiring is terminated into mechanically stable connection points
     * There are personality adapters to account for the level shifting, buffering and other I/O line adaptions that may be needed
     * While I like having blinking LED lights on every I/O line for debugging, others do not - so there is now a plug-in LED monitor slot for each set of 4x I/O lines
     * A generic I2C Expander plug in footprint.
    
    I have built several board variations for various different I2C
    Expander chips to take advantage of unique addressing, I/O levels,
    cost, etc - with the only thing changing between boards being the
    chip related stuff.  Maintaining and stocking several "slightly
    different" board designs gets expensive, both from both inventory
    and support perspectives.
    
    V1.0 is a prototype that seeks to validate the basic modular assumptions I'm making.
    
    
---


This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
