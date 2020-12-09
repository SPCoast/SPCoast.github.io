---
iseagle: true
sidebar: spcoast_sidebar
title: MRCS-cpNode-ProMini
project: MRCS-cpNode-ProMini
designer: Chuck Catania, Seth Neumann, John Plocher
fabricated: no
fab_date: 2020-12
status: released
release: yes
tags: [eagle, MRCS, Processor, LCB]
layout: eagle
image_path: MRCS-cpNode-ProMini.top.brd.png
tagline: Arduino ProMini based CMRI node in 2.71" form
overview: >
    
    cpNode with a ProMini instead of a BBLeo
    
    ## License: Creative Commons Attribution-NonCommercial-ShareAlike
    
    cpNode and I/O expander (IOX) boards have been updated to version
    3.0. The Original BareBones BBLeo is EOL and Unavailable, so this respin is done
    with a ProMini, which does not provide an independent USB serial interface.
    
      * Rev 3.0 boards are NOT backward compatible with previous versions. Software changes ARE needed.
    
    
    What does a cpNode do?
    
    cpNodes provide input and output (I/O) ports which connect to LEDs
    for signals, push buttons, turnout motors, block detectors, and
    other devices to a central computer for controlling model railroads.
    cpNodes may also be used as standalone controllers for staging,
    crossings and interlocking plants.
    
    A cpNode has:
    
      * 16 I/O lines with solder pads for LED limiting resistors
      * Screw terminal blocks or solder pads to connect external devices - see configurations below
      * CMRInet RS-422/485 Network Interface.  CMRInet is now NMRA Layout Control Specification S9-10
      * I2C interface for adding Input/Output Expander (IOX) boards for more i/o ports
      * All the i/o needed to control one end of a CTC siding, just add signals and detectors and switch motor drivers
      * Female headers to receive a BB-Leo (Arduino) processor available from Modern Device, use coupon code "cpnode" or order the cpNode LE option
      * I/O is configured in 8 bit groups, providing up to 144 lines when fully expanded with IOX16s and/or IOX32s
      * Use cpNodes as small, economical, CMRI nodes as is or customize the code to support applications requiring local intelligence
      * Standard "Sketch" (Arduino program) is compatible with JMRI or traditional CMRI BASIC/Visual Basic development tools
    
    
---


This technical documentation is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike](https://creativecommons.org/licenses/by-nc-sa/3.0/)
