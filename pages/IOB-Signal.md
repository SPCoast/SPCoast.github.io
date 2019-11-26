---
iseagle: true
sidebar: spcoast_sidebar
title: IOB-Signal
project: IOB-Signal
designer: John Plocher
fabricated: no
fab_date: 
status: released
release: yes
tags: [eagle, SPCoast]
layout: eagle
tagline: IOB Interface drives 2x Signal Heads via a RJ45/8 connector.
overview: >
    
    Fixed P1/P2 and P3/P4 reversals, caused red and yellow indications to be transposed.  Oops.
artifacts:
  - path: /versions/IOB-Signal/IOB-Signal_array.scr
    tag: IOB-Signal_array.scr
    type: download
    post: Eagle SCRipt
  - path: /versions/IOB-Signal/PanelTemplate.brd
    tag: PanelTemplate.brd
    type: download
    post: Eagle PCB file
---

## doc

PNP Ready: IOB Signal interface for the [I2C-7311](/pages/I2C-7311) IO expansion board and a [RJ45 SignalHead Adapter](/pages/Adapter-RJ45-SignalHead) board.

  * pin 1: 5vDC
  * pin 2: Head1-A
  * pin 3: Head1-B
  * pin 4: Head2-A
  * pin 5: Head2-B
  * pin 6: GND

Logic - write a total of 4 bits to the desired expander nibble, 2 bits per head:


| Head1 |  bit4 |  bit3  |  bit1  |  bit0  |  Indication    |
|------ | :----:| :----: | :----: | :----: | :----------    |
|       |   -   |   -    |   0    |   0    |  0b00 = GREEN  |
|------ | ----- | -----  | -----  | -----  | -----------    |
|       |   -   |   -    |   0    |   1    |  0b01 = RED    |
|------ | ----- | -----  | -----  | -----  | -----------    |
|       |   -   |   -    |   1    |   0    |  0b10 = YELLOW |
|------ | ----- | -----  | -----  | -----  | -----------    |
|       |   -   |   -    |   1    |   1    |  0b11 = DARK   |
|------ | ----- | -----  | -----  | -----  | -----------    |
 
| Head2 |  bit4 |  bit3  |  bit1  |  bit0  |  Indication    |
|------ | :----:| :----: | :----: | :----: | :----------    |
|       |   0   |   0    |   -    |   -    |  0b00 = GREEN  |
|------ | ----- | -----  | -----  | -----  | -----------    |
|       |   0   |   1    |   -    |   -    |  0b01 = RED    |
|------ | ----- | -----  | -----  | -----  | -----------    |
|       |   1   |   0    |   -    |   -    |  0b10 = YELLOW |
|------ | ----- | -----  | -----  | -----  | -----------    |
|       |   1   |   1    |   -    |   -    |  0b11 = DARK   |
|------ | ----- | -----  | -----  | -----  | -----------    |





This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
