---
iseagle: true
sidebar: spcoast_sidebar
title: MRCS-Morse-Code-Buzzer
project: MRCS-Morse-Code-Buzzer
designer: John Plocher
fabricated: yes
fab_date: 2017-08
status: released
release: yes
tags: [eagle, MRCS]
layout: eagle
tagline: Morse Code Buzzer Board
overview: >
    
    v3.0 20170815
---

## doc

On many operations-oriented model railroads, particularly those
which a time-table and train-order (TT&TO) or tower-based dispatching
system, there is a need to provide telephone communications between
the dispatcher and the agent/operators. However, even on fairly
large model railroads with multiple agent/operators, the physical
distances between the operator positions are often insufficient to
allow the operators to reliably distinguish that “hey that’s my
phone ringing.”

The Morse Code Buzzer Controller board controls up to seven stations,
tapping out each ringing station's Telegraph code in Railroad Morse.
An additional output can be designated an “ambience” buzzer that
will randomly play one of several canned messages. These could be
train orders, news reports, or “inside jokes”

The board accepts a push button input, stops when the phone goes
off-hook (phone must have a suitable contact to provide an isolated
ground) and will drive loads of up to 0.5 Amp at up to 48 Volts DC.
All buzzer/sounder devices must use the same supply.  Sounders must
have have a coil resistance of greater than 40 ohms if using a 12V
supply.

Requires a 6-9 VDC power supply rated at at least 0.5A. not included.

The on-board Arduino Pro-Mini runs the
["station buzzers" sketch](https://github.com/stevew1154/station_buzzers)
by Steve Williams.  




This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
