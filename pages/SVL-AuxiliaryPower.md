---
iseagle: true
sidebar: spcoast_sidebar
title: SVL-AuxiliaryPower
project: SVL-AuxiliaryPower
designer: John Plocher
fabricated: yes
fab_date: 2018-08
status: released
release: yes
tags: [eagle, SPCoast, Misc]
layout: eagle
image_path: 3.0/SVL-AuxiliaryPower-3.0.top.brd.png
tagline: SVL Aux Power - local distribution panel
overview: >
    
    Power source can be a DCC Booster, combining power distribution with the ability to build smart accessories based on stationary decoders
    
artifacts:
  - path: /versions/SVL-AuxiliaryPower/PTC-ruef110-PolySwitch.pdf
    tag: PTC-ruef110-PolySwitch.pdf
    type: download
    post: Documentation
  - path: /versions/SVL-AuxiliaryPower/eagle.epf
    tag: eagle
    type: download
    post: 
---

## Documentation

Silicon Valley Lines' model railroad layout uses a dedicated power
bus for all layout animations (street lighting, building lights,
signs, sound modules...) This board is the interface between that
high power bus and local (per module or per area) low power needs.

For layout animation and lighting, think "simple 555 based circuits",
flashing emergency vehicle lights, streetlights, "arduinos" and
"grain of wheat/rice bulbs".  These circuits need:

  * 12v for motors/animation
  * 9v for lights (derated from 12 to make them last longer)
  * 5v for "logic" circuits
  * 1.5v for structure lights
  * DCC for accessory decoders

This device can interface to the DCC Accssory bus or a dedicated 12VDC bus and provides:

  * 2x user adjustable switching supply outputs (1.3v - 30v @ 1A),
  * a rectified/filtered 12-14vDC and
  * A 1A fused DCC feed

The regulation is done by Buck Step-down LM2596 Power Converter Module DC 4.0~40 1.3-37V with LED voltage feedback
See http://www.ebay.com/itm/222245521575



This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
