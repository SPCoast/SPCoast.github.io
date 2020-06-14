---
iseagle: true
sidebar: spcoast_sidebar
title: IO4-Turtle
project: IO4-Turtle
designer: John Plocher
fabricated: yes
fab_date: 2018-03
image_path: IO4-Turtle-Graphic.png
status: released
release: yes
tags: [eagle, SPCoast, Appliance]
layout: eagle
tagline: IO4 Tortoise driver with occupancy and point position feedback
overview: >
    
    Carrier board, DFM, feedback LEDS that don't pass tortoise current and
    IO4 Tortoise driver with occupancy and point position feedback
    
images:
  - image_path: /versions/IO4-Turtle/IO4-Turtle-Graphic.png
    title: IO4-Turtle-Graphic
  - image_path: /versions/IO4-Turtle/Molex-on-Tortoise-1.jpg
    title: Molex-on-Tortoise-1
  - image_path: /versions/IO4-Turtle/Molex-on-Tortoise-2.jpg
    title: Molex-on-Tortoise-2
  - image_path: /versions/IO4-Turtle/Molex-on-Tortoise-3.jpg
    title: Molex-on-Tortoise-3
artifacts:
  - path: /versions/IO4-Turtle/IO4-Turtle.SMD-parts.csv
    tag: IO4-Turtle.SMD-parts
    type: download
    post: 
  - path: /versions/IO4-Turtle/IO4-Turtle_array.scr
    tag: IO4-Turtle_array.scr
    type: download
    post: Eagle SCRipt
  - path: /versions/IO4-Turtle/lm1117-Datasheet.pdf
    tag: lm1117-Datasheet.pdf
    type: download
    post: Documentation
---

## Documentation

This is an adaptation of my older PIC-based ExpressPCB Turtle
project, which is why the version numbers start at 4….  It has
evolved quite a bit, in form factor and functionality as it has
been used on my layout.

This board mounts on a Tortoise via a sweat-soldered right angle
Molex M-M connector, plugs into an [IOB-Turtle](/pages/IOB-Turtle)
or other IO4 compatible port.

The Tortoise provides:


 * OS section occupancy (so you don't throw a turnout out from under a train...),
 * Turnout point position feedback (Normal, in transit, Diverging)
 * easy frog polarity changes for dealing with wiring mishaps
 * easy Normal/Reverse changes for when the Normal route thru a turnout needs to go the other way.
 * Tortoise motor debouncing when it reaches the end of travel
 * feedback LEDs to show Occupancy (yellow) and commanded position (red/green)


It uses my standard IO4 RJ12/6 wiring interface:


 * pin 1: 9-12vDC
 * pin 2: !DIVERGING - Turnout Position Feedback - low = Diverging, high = not diverging
 * pin 3: !NORMAL    - Turnout Position Feedback - low = Normal, high = not normal
 * pin 4: !OCCUPIED  - Detector Feedback - low = occupied, high = empty
 * pin 5: !MOTOR     - Motor Control Input - Low = Normal, High = Diverging
 * pin 6: GND

It also connects to the local DCC track power feed and to the turnout's isolated-for-detection-purposes stock and frog rails.



## doc

This is an adaptation of my older PIC-based ExpressPCB Turtle
project, which is why the version numbers start at 4….  It has
evolved quite a bit, in form factor and functionality as it has
been used on my layout.

This board mounts on a Tortoise via a sweat-soldered right angle
Molex M-M connector, plugs into an [IOB-Turtle](/pages/IOB-Turtle)
or other IO4 compatible port.

The Tortoise provides:


 * OS section occupancy (so you don't throw a turnout out from under a train...),
 * Turnout point position feedback (Normal, in transit, Diverging)
 * easy frog polarity changes for dealing with wiring mishaps
 * easy Normal/Reverse changes for when the Normal route thru a turnout needs to go the other way.
 * Tortoise motor debouncing when it reaches the end of travel
 * feedback LEDs to show Occupancy (yellow) and commanded position (red/green)


It uses my standard IO4 RJ12/6 wiring interface:


 * pin 1: 9-12vDC
 * pin 2: !DIVERGING - Turnout Position Feedback - low = Diverging, high = not diverging
 * pin 3: !NORMAL    - Turnout Position Feedback - low = Normal, high = not normal
 * pin 4: !OCCUPIED  - Detector Feedback - low = occupied, high = empty
 * pin 5: !MOTOR     - Motor Control Input - Low = Normal, High = Diverging
 * pin 6: GND

It also connects to the local DCC track power feed and to the turnout's isolated-for-detection-purposes stock and frog rails.




This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
