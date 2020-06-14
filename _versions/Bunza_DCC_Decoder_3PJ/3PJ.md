---
iseagle: true
layout: eagle
sidebar: spcoast_sidebar
project: Bunza_DCC_Decoder_3PJ
title: 3PJ
designer: Geoff Bunza
fabricated: yes
fab_date: 2020.05
status: private
release: no
tags: [eagle, MRCS]
tagline: GBunza DCC Decoder v3PJ
overview: >
    
    
images:
  - image_path: /versions/Bunza_DCC_Decoder_3PJ/3PJ/Bunza_DCC_Decoder_3PJ_array-3PJ.brd.png
    title: Board
  - image_path: /versions/Bunza_DCC_Decoder_3PJ/3PJ/Bunza_DCC_Decoder_3PJ-3PJ.brd.png
    title: Board
  - image_path: /versions/Bunza_DCC_Decoder_3PJ/3PJ/Bunza_DCC_Decoder_3PJ-3PJ.bot.brd.png
    title: Bot Silk
  - image_path: /versions/Bunza_DCC_Decoder_3PJ/3PJ/Bunza_DCC_Decoder_3PJ-3PJ.top.brd.png
    title: Top Silk
  - image_path: /versions/Bunza_DCC_Decoder_3PJ/3PJ/Bunza_DCC_Decoder_3PJ-3PJ.sch.png
    title: Schematic
  - image_path: /versions/Bunza_DCC_Decoder_3PJ/3PJ/Bunza_DCC_Decoder_3PJ_array-3PJ.top.brd.png
    title: Top Silk
  - image_path: /versions/Bunza_DCC_Decoder_3PJ/3PJ/Bunza_DCC_Decoder_3PJ_array-3PJ.bot.brd.png
    title: Bot Silk
artifacts:
  - path: /versions/Bunza_DCC_Decoder_3PJ/3PJ/Bunza_DCC_Decoder_3PJ-3PJ.gerbers.zip
    tag: Bunza_DCC_Decoder_3PJ.gerbers.zip
    type: download
    post: Gerber Fabrication files
  - path: /versions/Bunza_DCC_Decoder_3PJ/3PJ/Bunza_DCC_Decoder_3PJ-3PJ.parts.csv
    tag: Bunza_DCC_Decoder_3PJ.parts
    type: download
    post: Parts List (spreadsheet data)
  - path: /versions/Bunza_DCC_Decoder_3PJ/3PJ/Bunza_DCC_Decoder_3PJ_array-3PJ.gerbers.zip
    tag: Bunza_DCC_Decoder_3PJ_array.gerbers.zip
    type: download
    post: Gerber Fabrication files
  - path: /versions/Bunza_DCC_Decoder_3PJ/3PJ/Bunza_DCC_Decoder_3PJ_array-3PJ.parts.csv
    tag: Bunza_DCC_Decoder_3PJ_array.parts
    type: download
    post: Parts List (spreadsheet data)
---

## Bunza_DCC_Decoder_3PJ.bom

{:.partlist}
| Parts | Value | Package | Quantity | Library | Type/Feeder
|-
| C2, C3 | 0.1uf 25V | AXIAL-5MM | 2x | SparkFun-Capacitors | PTH
|-
| R18 | 1.3K | 0204V | 1x | resistor | PTH
|-
| D3 | 1N4148 | DO35-7 | 1x | diode | PTH
|-
| R17 | 5K | 0204V | 1x | resistor | PTH
|-
| OK1 | 6N137 | DIL08 | 1x | optocoupler | PTH
|-
| R12 | 10K | 0204V | 1x | resistor | PTH
|-
| C6, C7 | 22 | 7343-TE-D | 2x | cap-master | NONE
|-
| C1 | 22uf 25V | C050-035X075 | 1x | rcl | PTH
|-
| C8 | 270 pf | AXIAL-5MM | 1x | SparkFun-Capacitors | PTH
|-
| VR1 | 7805 | TO220V | 1x | linear | PTH
|-
| DCC1, DCC2 |  | 2.15/1.0 | 2x | wirepad | PTH
|-
| ARD_PRO_MINI |  | ARDUINO_MINI | 1x | SparkFun-Boards | PTH
|-
| B1 | DF05 | DB | 1x | rectifier | PTH
|-
| JP5 | MOT1 | 1X02 | 1x | SparkFun-Connectors | PTH
|-
| JP6 | MOT2 | 1X02 | 1x | SparkFun-Connectors | PTH
|-
| IC2 | SN754410 | DIP16 | 1x | HBridge | PTH
|-
| TP1, TP2, TP3 | TPTP10SQ | TP10SQ | 3x | testpad | NONE

## Bunza_DCC_Decoder_3PJ_array.bom

{:.partlist}
| Parts | Value | Package | Quantity | Library | Type/Feeder
|-
| JP5X11, JP5X12, JP5X13, JP5X14, JP5X15, JP6X11, JP6X12, JP6X13, JP6X14, JP6X15 |  | 1X02 | 10x | SparkFun-Connectors | PTH
|-
| DCC1X11, DCC1X12, DCC1X13, DCC1X14, DCC1X15, DCC2X11, DCC2X12, DCC2X13, DCC2X14, DCC2X15 |  | 2.15/1.0 | 10x | wirepad | PTH
|-
| R12X11, R12X12, R12X13, R12X14, R12X15, R17X11, R17X12, R17X13, R17X14, R17X15, R18X11, R18X12, R18X13, R18X14, R18X15 |  | 0204V | 15x | resistor | PTH
|-
| C6X11, C6X12, C6X13, C6X14, C6X15, C7X11, C7X12, C7X13, C7X14, C7X15 |  | 7343-TE-D | 10x | cap-master | NONE
|-
| ARD_PRO_MINIX11, ARD_PRO_MINIX12, ARD_PRO_MINIX13, ARD_PRO_MINIX14, ARD_PRO_MINIX15 |  | ARDUINO_MINI | 5x | SparkFun-Boards | PTH
|-
| C2X11, C2X12, C2X13, C2X14, C2X15, C3X11, C3X12, C3X13, C3X14, C3X15, C8X11, C8X12, C8X13, C8X14, C8X15 |  | AXIAL-5MM | 15x | SparkFun-Capacitors | PTH
|-
| C1X11, C1X12, C1X13, C1X14, C1X15 |  | C050-035X075 | 5x | rcl | PTH
|-
| B1X11, B1X12, B1X13, B1X14, B1X15 |  | DB | 5x | rectifier | PTH
|-
| OK1X11, OK1X12, OK1X13, OK1X14, OK1X15 |  | DIL08 | 5x | optocoupler | PTH
|-
| IC2X11, IC2X12, IC2X13, IC2X14, IC2X15 |  | DIP16 | 5x | HBridge | PTH
|-
| D3X11, D3X12, D3X13, D3X14, D3X15 |  | DO35-7 | 5x | diode | PTH
|-
| VR1X11, VR1X12, VR1X13, VR1X14, VR1X15 |  | TO220V | 5x | linear | PTH
|-
| TP1X11, TP1X12, TP1X13, TP1X14, TP1X15, TP2X11, TP2X12, TP2X13, TP2X14, TP2X15, TP3X11, TP3X12, TP3X13, TP3X14, TP3X15 |  | TP10SQ | 15x | testpad | NONE
