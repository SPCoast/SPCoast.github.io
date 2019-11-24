---
iseagle: true
sidebar: spcoast_sidebar
title: Loconet-QuadOD
project: Loconet-QuadOD
designer: John Plocher
fabricated: no
fab_date: 
status: experimental
release: yes
layout: eagle
tags: [SPCoast, eagle]
tagline: LocoNet Quad Detector baseboard
overview: >
    
    An Arduino Pro Mini with 4x DCC-OD/cpOD sockets and LocoNet-style communications that can be used as a building block for a stand alone Loconet Occupancy Detector.
    
artifacts:
  - path: /versions/Loconet-QuadOD/Loconet-QuadOD.gerbers.zip
    tag: Loconet-QuadOD.gerbers
    type: download
    post: 
  - path: /versions/Loconet-QuadOD/Loconet-QuadOD.parts.csv
    tag: Loconet-QuadOD.parts
    type: download
    post: 
---

## doc

LN Quad Detector

A variation on [IO4-QuadOD](/IO4-QuadOD.html) that replaces the
WemosD1 & IO4 connections with an Arduino Pro Mini and LocoNet-style
communications.

This simple 4-pack module should end up with a BOM cost between $5
and $10, so a full stand alone quad detector pack would run about
$60 with detector boards.

The [MRRWA Embedded Loconet library](https://github.com/mrrwa/LocoNet)
includes support for LN-SV V2 configuration management, which is
also supported by JMRI; it should be pretty easy to write an
addressable Detector sketch (TBD) with assorted XML definitions
suitable for DecoderPro3...

This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
