---
iseagle: true
sidebar: spcoast_sidebar
title: MRCS-BB-Wemos
project: MRCS-BB-Wemos
designer: John Plocher
fabricated: yes
fab_date: 2023-01
status: experimental
publish: yes
tags: [MRCS, SPCoast, eagle]
layout: eagle
image_path: MRCS-BB-Wemos.top.brd.png
tagline: MRCS cpNode BB-Wemos
overview: >
    WeMos board adapter for BB-Leo format to fit on cpNode
    
    This board contains a Wemos D1 processor, 1A regulator, level shifters and an MCP23017 to provide a rough equivalent to a BB-Leo.
    
    The Wemos D1 has considerably more code space than a ProMini/Leonardo
    and could eventually support a "local fall back" mode when no CMRINet
    is present and may support other protocols over WiFi.  It will use
    John Plochers forthcoming cpNode sketch.
    
    ## License: Creative Commons Attribution-NonCommercial-ShareAlike
artifacts:
  - path: /versions/MRCS-BB-Wemos/BB-Wemos BOM 20190829.xlsx
    tag: BB-Wemos BOM 20190829.xlsx
    type: download
    post: Spreadsheet
  - path: /versions/MRCS-BB-Wemos/MRCS-BB-Wemos Layout.pdf
    tag: MRCS-BB-Wemos Layout.pdf
    type: download
    post: Documentation
  - path: /versions/MRCS-BB-Wemos/MRCS-BB-Wemos Schematic.pdf
    tag: MRCS-BB-Wemos Schematic.pdf
    type: download
    post: Documentation
  - path: /versions/MRCS-BB-Wemos/MRCS-BB-Wemos.SMD-parts.csv
    tag: MRCS-BB-Wemos.SMD-parts
    type: download
    post: 
  - path: /versions/MRCS-BB-Wemos/MRCS-BB-Wemos.zip
    tag: MRCS-BB-Wemos
    type: download
    post: 
  - path: /versions/MRCS-BB-Wemos/MRCS-BB-Wemos_array.SMD-parts.csv
    tag: MRCS-BB-Wemos_array.SMD-parts
    type: download
    post: 
  - path: /versions/MRCS-BB-Wemos/MRCS-BB-Wemos_array.scr
    tag: MRCS-BB-Wemos_array.scr
    type: download
    post: Eagle SCRipt
---

## Documentation

This board contains a Wemos D1 processor, 1A regulator, level shifters and an MCP23017 to provide a rougth equivalent to a BB-Leo.
This board has considerably more code space and will eventually support a "local fall back" mode when no CMRINet is present and may
support other protocols over WiFi.  It will use John Plochers forthcoming cpNode sketch.


This technical documentation is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike](https://creativecommons.org/licenses/by-nc-sa/3.0/)
