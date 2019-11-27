---
iseagle: true
sidebar: spcoast_sidebar
title: RFID-RC522-Wemos
project: RFID-RC522-Wemos
designer: John Plocher
fabricated: yes
fab_date: 2017-02
status: experimental
release: yes
tags: [eagle, SPCoast]
layout: eagle
tagline: RFID reader based on RC522 module with Wemos and LCD
overview: >
    
    Initial version, talks rudamentary MQTT
---

## doc

Wemos RFID / LCD device

I found a cheap RC522 RFID card reader on eBay [eBay example](https://www.ebay.com/i/112341068592)
and wanted to experiment with it.  In the future, I may
use this to do location-based interactions with the crews (i.e.,
switch list identification, local control unlocking, etc)

At this point, the Wemos D1 Mini can send MQTT messages via WiFi that can be
consumed by other nodes - or even JMRI.




This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
