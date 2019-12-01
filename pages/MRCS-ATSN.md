---
iseagle: true
sidebar: spcoast_sidebar
title: MRCS-ATSN
project: MRCS-ATSN
designer: John Plocher
fabricated: yes
fab_date: 2017-08
status: released
release: yes
tags: [eagle, MRCS, Telephone]
layout: eagle
tagline: Dispatcher/Operator Telephone board / Electronic Speech Telephone Network board (ASTN)
overview: >
    
    This is a Model Railroad Control Systems design by Clint Gilliland,
    Seth Neumann and John Plocher.
    
      1. Change headers for external pots to 4 position on ALL 3 pots, so there is a ground on the (new) position 4.  Handy if the user has bought some shielded wire and wants to use it on all pots.  Should help with noise and RF (cell phone) interference.
      2. Remove C5, was a roll off to prevent pops but really didn’t help
      3. Jumper and new 1K resistor  to bring mic preamp down to unit gain for line level input.  This is intended for interfacing with line level mic sources such as computer output from Skype for remote dispatching.
      4. Add pads for 100pF monolithic caps on mic in, audio out and both sides of xfmr facing the world.  This is to filter out any cell phone interference
      5. Made new component for inexpensive (did I say “cheap?) banggood coupling xmfr and put in parallel with TY145P.  Cost reduction.
    
    
artifacts:
  - path: /versions/MRCS-ATSN/EI14-Isolation-Transformer.docx
    tag: EI14-Isolation-Transformer
    type: download
    post: 
  - path: /versions/MRCS-ATSN/EI14-Isolation-Transformer.pdf
    tag: EI14-Isolation-Transformer.pdf
    type: download
    post: Documentation
---

## doc

## Dispatcher/Operator Telephone board
### Electronic Speech Telephone Network board  (ASTN)

(Designed by MRCS)

The Electronic Speech Telephone Network (ASTN) board provides the
electronics and connections for building a telephone for a Dispatcher
or Operator for use with a model railroad telephone system using
either a microphone/speaker/footswitch arrangement or using an
inexpensive computer headset.  The Mic/Speaker/Foot switch arrangement
is recommended where the dispatcher or operator will be in a
sound-isolated environment and the headset (preferably noise
cancelling) is recommended for Operators and Dispatchers who will
be in the layout room.  Features include:

  * Supports either Dynamic or Electret microphones
  * Independent control of outbound, inbound and "break-in" volume
  * Break in volume is the level heard by the user when depressing the footswitch (prototype train order operators would break in if there was an error during an order or repeat as a safety measure)
  * Can be used to "modernize" a classic candlestick type phone for better performance in a noisy layout room
  * supports mono or stereo inputs and outputs
  * optional phase reversal on output to help tune maximum volume without feedback
  * No DC load on the dispatcher's line
  * line level output for powered speakers or input to an external amplifier
  * uses 24 VDC
  * optional remote volume controls
  * transmit LED indicator

This is a Model Railroad Control Systems Telephony design by Clint Gilliland,
Seth Neumann and John Plocher.

You are free to download the files and make your own or you can
purchase bare boards or assembled and tested product from
[Model Railroad Control Systems](http://www.modelrailroadcontrolsystems.com/).



This technical documentation is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike](https://creativecommons.org/licenses/by-nc-sa/3.0/)
