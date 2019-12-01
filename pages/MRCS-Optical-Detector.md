---
iseagle: true
sidebar: spcoast_sidebar
title: MRCS-Optical-Detector
project: MRCS-Optical-Detector
designer: John Plocher
fabricated: yes
fab_date: 2017-12
status: released
release: yes
tags: [eagle, MRCS]
layout: eagle
tagline: Ambiant light optical detector based on GBunza DAPD with Chubb style hysteresis
overview: >
    
    DFM, PTH parts, offboard detectors...
    
---

## doc

Optical Position Detectors are useful when precise position detection
is required (clearing a staging throat, for example), when the area
to be detected is small (an "OS" section in a CTC system) or where
resistance wheel sets cannot be applied and current detection can't
be used.  The Enhanced Optical Position Detector is based on Geoff
Bunza's DAPD and provides a fixed turn-on and turn-off delay and
high power output stage similar to Bruce Chubb's DCC-OD (so if you
need an optical detector that's electrically compatible with a cpOD
or DCC-OD, EOPD is for you!).

The EOPD uses Geoff's self-calibrating detection circuit, so you
don't need to adjust for ambient light level.  Note the circuit
won't work in the dark unless you substitute infrared Photo transistors
and provide an infrared illumination source.  The supply voltage
range is 5-15 volts and the output is a active low (0/gnd is true)
open collector which will sink up to 600 mA at up to 40VDC.  Size
is 1.15" x 1.75 x 0.5" high"


Either 2 PT-19 photo transistors or
[“Da Fingah”](/pages/IO4-IR-Detector-GBunza-Fingers) will work with this
board. One is used as an ambient light reference and another is
placed between the rails. You may solder the reference photodetector
onto the board if the board will be mounted where is has the same
illumination as the track or both may be mounted remotely.


This detector is compatible with the Modular Signaling System (MSS) Optical Detector


This technical documentation is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike](https://creativecommons.org/licenses/by-nc-sa/3.0/)
