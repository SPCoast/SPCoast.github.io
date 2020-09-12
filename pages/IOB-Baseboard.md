---
iseagle: true
sidebar: spcoast_sidebar
title: IOB-Baseboard
project: IOB-Baseboard
image_path: IOB-Baseboard-Graphic.png
designer: John Plocher
author: John Plocher
fabricated: yes
fab_date: 2020.09
status: released
release: yes
tags: [eagle, SPCoast]
layout: eagle
tagline: IOB Baseboard - wiring termination and I2C / Power bus management
overview: >
    
    This board was originally produced to help me build control panels for
    my model railroad - I needed to connect many different buttons, switches
    and lights to an Arduino, and also connect the Arduino to a
    communications bus (Ethernet, CAN or Loconet), and I couldn\'t find
    anything that had both high IO point density AND visual feedback.
    
    The design moved from overly generic and/or overly specialized
    designs to a generic design with daughterboards that encapsulate the
    appliance-specific buffering and logic. The benefits provided by these
    IOB boards include:
    
    -   Improved I/O bank utilization (leftover capacity is now a multiple
        of 4-bit daughtercard instead of 16-bit I2C card\...)
    -   Riser height eliminates having to custom cut 3M track
    -   Allows custom circuitry to be added to Signal, Detector and Turtle
        drivers
    
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
    
    
    ### Cautions
    
    With several hundred IO loads, and up to 256 external breakout devices,
    a suitable power supply (or supplies) must be used.
    
    In practice, a 3A 9-12VDC supply a good choice for most small to medium
    sized control points.
    
    This supply needs to power the core processor, its direct IO loads, the
    I2C expander chain AND provide \~100mA to each IO4 device. Instead of
    relying on the Arduino\'s onboard regulated supply (which is only good
    for about 100mA itself), each board has its own regulator with a common
    supply feed that can handle up to 4A @ 12v. If more power is needed, the
    daisy chained power feed thru can be replaced with a per-board
    independent supply.
    
images:
  - image_path: /versions/IOB-Baseboard/IOB-Baseboard-Graphic.png
    title: IOB-Baseboard-Graphic
artifacts:
  - path: /versions/IOB-Baseboard/IOB-Baseboard.SMD-parts.csv
    tag: IOB-Baseboard.SMD-parts
    type: download
    post: 
  - path: /versions/IOB-Baseboard/IOB-Baseboard.gstencil
    tag: IOB-Baseboard
    type: download
    post: 
---


This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
