---
iscontrolpoint: true
sidebar: spcoast_sidebar
title: CP_Watsonville_South
project: CP_Watsonville_South
layout: arduino
tags: [SPCoast, arduino]
tagline: description not provided
overview: >
    
artifacts:
  - path: /sketches/CP_Watsonville_South/CP_Watsonville_South.ino
    tag: CP_Watsonville_South.ino
    type: download
    post: Arduino Sketch
  - path: /sketches/CP_Watsonville_South/sketch.json
    tag: sketch
    type: download
    post: 
---

## Documentation

<pre>
    South end of Watsonville Staging Yard.  MP 90
    Yard ladder, reverse loop and departure track.  See also Watsonville North.
    < Railroad West/North                             Railroad East/South >
                                                       O-| 904Na
    Departure <================DAT= ==== 1T1========+==== =========================\
                                    |-OO 904Sab      \901                            \
                                                 903T2\                              |
    Yard Track 1 >=========d==1SAT= ===d-3T2===========d\  YLAD                       |
                                    |-O 902sa         903\d-903T1                     |
    Yard Track 2 >=========d==2SAT= ===d 5T2=============d\                          ROCC (reverse LOOP)
                                    |-O 902sb           905\d                         |
    Yard Track 3 >=========d==3SAT= ===d 7T2===============d\                         |
                                    |-O 902sc             907\d                       |
    Yard Track 4 >=========d==4SAT= ===d 9T2=================d\  OO-| 902Nab         /
                                    |-O 902sd               909\=d= ===============/
                           ^    [MC]   ^                    ^
                          IR           IR                  IR  ('d' = IR Detectors)
    This 'CP' is all within yard limits of Watsonville Staging Yard.
    There is a MCall for departing trains to contact the dispatcher for authority.
    Trains on a Yard Track exit "Southbound", traverse the reverse loop to become "Northbound"
    and exit via the departure track and Watsonville North.
    Dwarf Signals control the exit from each Yard Track.
    Optical sensors ('d') are used for Switch Occupancy and Yard Track stopping
    position and switch fouling detection
    YLAD = Block detector plus 4x IR (point fouling) + 4x (yard fouling) IR detectors
    YARDx = Block detector + IR detector   IR detector is used to indicate where to stop a train
    There are 5 switches in CP Watsonville South:
        SW1 for the reverse loop Departure track (usually left Normal)
        SW3 ... SW9 for the Yard Track exit ladder
    Switches are Power Routing, so Turtle does not power frog...
    Sw 3,5,7, and 9 are all part of the same block detection block
    There are 2 Signals that control traffic - 2 (Yard Track access) and 4 (Departure track access)
     Southbound Approach on Departure Track:  DAT
     Southbound Approach on Yard Track:  [1-4]SAT
     Northbound Approach from LOOP: LOOP
    Possible routes:
        (A) Normal Operations NX:  eNter from Yard_n, exit on DT
            Leave Yard from ____________ via LOOP and Departure Track
                        Yard Track 1
                        Yard Track 2
                        Yard Track 3
                        Yard Track 4
            Set switches as desired, S2 RIGHT, S4 LEFT,FLEET
        (B) Infrequent, used during layout operations setup: eNter from DT, exit on Yard_n
            Enter ____________ from Departure track and LOOP
              Yard Track 1
              Yard Track 2
              Yard Track 3
              Yard Track 4
            Set switches as desired, S2 LEFT, S4 RIGHT,FLEET
        (C) Turn Train from Departure track and LOOP back out through Departure Track
            Set all switches Normal, S4 RIGHT.
            When train is in LOOP and 1T1 UNOCCUPIED, set SW1 Reverse, S4 STOP, then S4 LEFT
</pre>
<blockquote>
<table border=1 style="font-family: monospace;width: 80%;">
<tr>
<th colspan="9"> Controls for CP_Watsonville_S
</th>
</tr>
<tr>
<th> Byte
</th>
<td align="center">bit 0   
</td>
<td align="center"> bit 1   
</td>
<td align="center"> bit 2   
</td>
<td align="center"> bit 3   
</td>
<td align="center"> bit 4   
</td>
<td align="center"> bit 5   
</td>
<td align="center"> bit 6   
</td>
<td align="center"> bit 7   
</td>
</tr>
<tr>
<th> 0 
</th>  
<td align="center"> 901NWS  
</td>
<td align="center"> 901RWS  
</td>
<td align="center"> 903NWS  
</td>
<td align="center"> 903RWS  
</td>
<td align="center"> 905NWS  
</td>
<td align="center"> 905RWS  
</td>
<td align="center"> 907NWS  
</td>
<td align="center"> 907RWS  
</td>
</tr>
<tr>
<th> 1 
</th>  
<td align="center"> 909NWS  
</td>
<td align="center"> 909RWS  
</td>
<td align="center"> 902SGS  
</td>
<td align="center"> 902NGS  
</td>
<td align="center"> 902HS   
</td>
<td align="center"> 904SGS  
</td>
<td align="center"> 904NGS  
</td>
<td align="center"> 904HS   
</td>
</tr>
<tr>
<th> 2 
</th>  
<td align="center"> RPONS   
</td>
<td align="center"> RPOFFS  
</td>
<td align="center"> BPONS   
</td>
<td align="center"> BPOFFS  
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
<td align="center"> MC1S    
</td>
</tr>
</table>
</blockquote>
<blockquote>
<table border=1 style="font-family: monospace;width: 80%;">
<tr>
<th colspan="9"> Indications for CP_Watsonville_S
</th>
</tr>
<tr>
<th> Byte
</th>
<td align="center">bit 0   
</td>
<td align="center"> bit 1   
</td>
<td align="center"> bit 2   
</td>
<td align="center"> bit 3   
</td>
<td align="center"> bit 4   
</td>
<td align="center"> bit 5   
</td>
<td align="center"> bit 6   
</td>
<td align="center"> bit 7   
</td>
</tr>
<tr>
<th> 0 
</th>  
<td align="center"> 901NWK  
</td>
<td align="center"> 901RWK  
</td>
<td align="center"> 903NWK  
</td>
<td align="center"> 903RWK  
</td>
<td align="center"> 905NWK  
</td>
<td align="center"> 905RWK  
</td>
<td align="center"> 907NWK  
</td>
<td align="center"> 907RWK  
</td>
</tr>
<tr>
<th> 1 
</th>  
<td align="center"> 909NWK  
</td>
<td align="center"> 909RWK  
</td>
<td align="center"> 902SGK  
</td>
<td align="center"> 902NGK  
</td>
<td align="center"> 902TEK  
</td>
<td align="center"> 904SGK  
</td>
<td align="center"> 904NGK  
</td>
<td align="center"> 904TEK  
</td>
</tr>
<tr>
<th> 2 
</th>  
<td align="center"> 901T1K  
</td>
<td align="center"> 903T1K  
</td>
<td align="center"> 905T1K  
</td>
<td align="center"> 907T1K  
</td>
<td align="center"> 909T1K  
</td>
<td align="center"> 903T2K  
</td>
<td align="center"> 905T2K  
</td>
<td align="center"> 907T2K  
</td>
</tr>
<tr>
<th> 3 
</th>  
<td align="center"> 909T2K  
</td>
<td align="center"> 903T3K  
</td>
<td align="center"> 905T3K  
</td>
<td align="center"> 907T3K  
</td>
<td align="center"> 909T3K  
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
</tr>
<tr>
<th> 4 
</th>  
<td align="center"> 1SATK   
</td>
<td align="center"> 2SATK   
</td>
<td align="center"> 3SATK   
</td>
<td align="center"> 4SATK   
</td>
<td align="center"> 1SAATK  
</td>
<td align="center"> 2SAATK  
</td>
<td align="center"> 3SAATK  
</td>
<td align="center"> 4SAATK  
</td>
</tr>
<tr>
<th> 5 
</th>  
<td align="center"> - - -   
</td>
<td align="center"> DATK    
</td>
<td align="center"> YLADK   
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
<td align="center"> MC1K    
</td>
</tr>
<tr>
<th> 6 
</th>  
<td align="center"> RSHORTK 
</td>
<td align="center"> RTONK   
</td>
<td align="center"> ROCCK   
</td>
<td align="center"> ROFFK   
</td>
<td align="center"> BSHORTK 
</td>
<td align="center"> BTONK   
</td>
<td align="center"> BOCCK   
</td>
<td align="center"> BOFFK   
</td>
</tr>
</table>
</blockquote>
<blockquote>
<table border=1 style="font-family: monospace;width: 80%;">
<tr>
<th colspan="17"> FieldUnit for CP_Watsonville_S
</th>
</tr>
<tr>
<th> Expander
</th>
<td align="center">bit 0   
</td>
<td align="center"> bit 1   
</td>
<td align="center"> bit 2   
</td>
<td align="center"> bit 3   
</td>
<td align="center"> bit 4   
</td>
<td align="center"> bit 5   
</td>
<td align="center"> bit 6   
</td>
<td align="center"> bit 7   
</td>
<td align="center"> bit 8   
</td>
<td align="center"> bit 9   
</td>
<td align="center"> bit 10  
</td>
<td align="center"> bit 11  
</td>
<td align="center"> bit 12  
</td>
<td align="center"> bit 13  
</td>
<td align="center"> bit 14  
</td>
<td align="center"> bit 15  
</td>
</tr>
<tr>
<th> 0 
</th>  
<td align="center"> i 901NW 
</td>
<td align="center"> i 901RW 
</td>
<td align="center"> i 901T1 
</td>
<td align="center"> o T901  
</td>
<td align="center"> i 903NW 
</td>
<td align="center"> i 903RW 
</td>
<td align="center"> i 903T1 
</td>
<td align="center"> o T903  
</td>
<td align="center"> i 905NW 
</td>
<td align="center"> i 905RW 
</td>
<td align="center"> i 905T1 
</td>
<td align="center"> o T905  
</td>
<td align="center"> i 907NW 
</td>
<td align="center"> i 907RW 
</td>
<td align="center"> i 907T1 
</td>
<td align="center"> o T907  
</td>
</tr>
<tr>
<th> 1 
</th>  
<td align="center"> i 909NW 
</td>
<td align="center"> i 909RW 
</td>
<td align="center"> i 909T1 
</td>
<td align="center"> o T909  
</td>
<td align="center"> i RSHORT
</td>
<td align="center"> i RTON  
</td>
<td align="center"> i ROCC  
</td>
<td align="center"> o ROFF  
</td>
<td align="center"> i BSHORT
</td>
<td align="center"> i BTON  
</td>
<td align="center"> i BOCC  
</td>
<td align="center"> o BOFF  
</td>
<td align="center"> o MC1   
</td>
<td align="center"> o XO11  
</td>
<td align="center"> o XO12  
</td>
<td align="center"> o XO13  
</td>
</tr>
<tr>
<th> 2 
</th>  
<td align="center"> i YLT   
</td>
<td align="center"> i DAT   
</td>
<td align="center"> i XI22  
</td>
<td align="center"> i XI23  
</td>
<td align="center"> i 903T2 
</td>
<td align="center"> i 905T2 
</td>
<td align="center"> i 907T2 
</td>
<td align="center"> i 909T2 
</td>
<td align="center"> i 903T3 
</td>
<td align="center"> i 905T3 
</td>
<td align="center"> i 907T3 
</td>
<td align="center"> i 909T3 
</td>
<td align="center"> i 1SAT  
</td>
<td align="center"> i 2SAT  
</td>
<td align="center"> i 3SAT  
</td>
<td align="center"> i 4SAT  
</td>
</tr>
<tr>
<th> 3 
</th>  
<td align="center"> i 1SAAT 
</td>
<td align="center"> i 2SAAT 
</td>
<td align="center"> i 3SAAT 
</td>
<td align="center"> i 4SAAT 
</td>
<td align="center"> o 902NAB1
</td>
<td align="center"> o 902NAB2
</td>
<td align="center"> o 902NAB3
</td>
<td align="center"> o 902NAB4
</td>
<td align="center"> o 902SA1
</td>
<td align="center"> o 902SA2
</td>
<td align="center"> o 902SB1
</td>
<td align="center"> o 902SB2
</td>
<td align="center"> o 902SC1
</td>
<td align="center"> o 902SC2
</td>
<td align="center"> o 902SD1
</td>
<td align="center"> o 902SD2
</td>
</tr>
<tr>
<th> 4 
</th>  
<td align="center"> o 904NA1
</td>
<td align="center"> o 904NA2
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
<td align="center"> o 904SAB1
</td>
<td align="center"> o 904SAB2
</td>
<td align="center"> o 904SAB3
</td>
<td align="center"> o 904SAB4
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
<td align="center"> - - -   
</td>
</tr>
</table>
</blockquote>
<blockquote>
<table border=1 style="font-family: monospace; width: 80%;">
<tr>
<th colspan="11" style="text-align:center;"> Expanders Wiring for CP_Watsonville_S
</th>
</tr>
<tr>
<th>  # </th>
<th>  Device
</th>
<th>  i2c
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</tr>
<tr>
<th rowspan=4> 0
</th>
<th rowspan=4>   MCP23017
</th>
<th rowspan=4> 0x00 
</th>
<td> 12 
</td>
<td> i 907NW 
</td>
<td> 8 
</td>
<td> i 905NW 
</td>
<td> 4 
</td>
<td> i 903NW 
</td>
<td> 0 
</td>
<td> i 901NW 
</td>
</tr>
<!-- row span -->
<td> 13 
</td>
<td> i 907RW 
</td>
<td> 9 
</td>
<td> i 905RW 
</td>
<td> 5 
</td>
<td> i 903RW 
</td>
<td> 1 
</td>
<td> i 901RW 
</td>
</tr>
<!-- row span -->
<td> 14 
</td>
<td> i 907T1 
</td>
<td> 10 
</td>
<td> i 905T1 
</td>
<td> 6 
</td>
<td> i 903T1 
</td>
<td> 2 
</td>
<td> i 901T1 
</td>
</tr>
<!-- row span -->
<td> 15 
</td>
<td> o T907 
</td>
<td> 11 
</td>
<td> o T905 
</td>
<td> 7 
</td>
<td> o T903 
</td>
<td> 3 
</td>
<td> o T901 
</td>
</tr>
<tr>
<th>  # </th>
<th>  Device
</th>
<th>  i2c
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</tr>
<tr>
<th rowspan=4> 1
</th>
<th rowspan=4>   MCP23017
</th>
<th rowspan=4> 0x01 
</th>
<td> 12 
</td>
<td> o MC1 
</td>
<td> 8 
</td>
<td> i BSHORT 
</td>
<td> 4 
</td>
<td> i RSHORT 
</td>
<td> 0 
</td>
<td> i 909NW 
</td>
</tr>
<!-- row span -->
<td> 13 
</td>
<td> o XO11 
</td>
<td> 9 
</td>
<td> i BTON 
</td>
<td> 5 
</td>
<td> i RTON 
</td>
<td> 1 
</td>
<td> i 909RW 
</td>
</tr>
<!-- row span -->
<td> 14 
</td>
<td> o XO12 
</td>
<td> 10 
</td>
<td> i BOCC 
</td>
<td> 6 
</td>
<td> i ROCC 
</td>
<td> 2 
</td>
<td> i 909T1 
</td>
</tr>
<!-- row span -->
<td> 15 
</td>
<td> o XO13 
</td>
<td> 11 
</td>
<td> o BOFF 
</td>
<td> 7 
</td>
<td> o ROFF 
</td>
<td> 3 
</td>
<td> o T909 
</td>
</tr>
<tr>
<th>  # </th>
<th>  Device
</th>
<th>  i2c
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</tr>
<tr>
<th rowspan=4> 2
</th>
<th rowspan=4>   MCP23017
</th>
<th rowspan=4> 0x02 
</th>
<td> 12 
</td>
<td> i 1SAT 
</td>
<td> 8 
</td>
<td> i 903T3 
</td>
<td> 4 
</td>
<td> i 903T2 
</td>
<td> 0 
</td>
<td> i YLT 
</td>
</tr>
<!-- row span -->
<td> 13 
</td>
<td> i 2SAT 
</td>
<td> 9 
</td>
<td> i 905T3 
</td>
<td> 5 
</td>
<td> i 905T2 
</td>
<td> 1 
</td>
<td> i DAT 
</td>
</tr>
<!-- row span -->
<td> 14 
</td>
<td> i 3SAT 
</td>
<td> 10 
</td>
<td> i 907T3 
</td>
<td> 6 
</td>
<td> i 907T2 
</td>
<td> 2 
</td>
<td> i XI22 
</td>
</tr>
<!-- row span -->
<td> 15 
</td>
<td> i 4SAT 
</td>
<td> 11 
</td>
<td> i 909T3 
</td>
<td> 7 
</td>
<td> i 909T2 
</td>
<td> 3 
</td>
<td> i XI23 
</td>
</tr>
<tr>
<th>  # </th>
<th>  Device
</th>
<th>  i2c
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</tr>
<tr>
<th rowspan=4> 3
</th>
<th rowspan=4>   MCP23017
</th>
<th rowspan=4> 0x03 
</th>
<td> 12 
</td>
<td> o 902SC1 
</td>
<td> 8 
</td>
<td> o 902SA1 
</td>
<td> 4 
</td>
<td> o 902NAB1 
</td>
<td> 0 
</td>
<td> i 1SAAT 
</td>
</tr>
<!-- row span -->
<td> 13 
</td>
<td> o 902SC2 
</td>
<td> 9 
</td>
<td> o 902SA2 
</td>
<td> 5 
</td>
<td> o 902NAB2 
</td>
<td> 1 
</td>
<td> i 2SAAT 
</td>
</tr>
<!-- row span -->
<td> 14 
</td>
<td> o 902SD1 
</td>
<td> 10 
</td>
<td> o 902SB1 
</td>
<td> 6 
</td>
<td> o 902NAB3 
</td>
<td> 2 
</td>
<td> i 3SAAT 
</td>
</tr>
<!-- row span -->
<td> 15 
</td>
<td> o 902SD2 
</td>
<td> 11 
</td>
<td> o 902SB2 
</td>
<td> 7 
</td>
<td> o 902NAB4 
</td>
<td> 3 
</td>
<td> i 4SAAT 
</td>
</tr>
<tr>
<th>  # </th>
<th>  Device
</th>
<th>  i2c
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</th>
<th>  Bit
</th>
<th>  Signal
</tr>
<tr>
<th rowspan=4> 4
</th>
<th rowspan=4>   MCP23017
</th>
<th rowspan=4> 0x04 
</th>
<td> 12 
</td>
<td> &nbsp;&nbsp;- - - 
</td>
<td> 8 
</td>
<td> &nbsp;&nbsp;- - - 
</td>
<td> 4 
</td>
<td> o 904SAB1 
</td>
<td> 0 
</td>
<td> o 904NA1 
</td>
</tr>
<!-- row span -->
<td> 13 
</td>
<td> &nbsp;&nbsp;- - - 
</td>
<td> 9 
</td>
<td> &nbsp;&nbsp;- - - 
</td>
<td> 5 
</td>
<td> o 904SAB2 
</td>
<td> 1 
</td>
<td> o 904NA2 
</td>
</tr>
<!-- row span -->
<td> 14 
</td>
<td> &nbsp;&nbsp;- - - 
</td>
<td> 10 
</td>
<td> &nbsp;&nbsp;- - - 
</td>
<td> 6 
</td>
<td> o 904SAB3 
</td>
<td> 2 
</td>
<td> &nbsp;&nbsp;- - - 
</td>
</tr>
<!-- row span -->
<td> 15 
</td>
<td> &nbsp;&nbsp;- - - 
</td>
<td> 11 
</td>
<td> &nbsp;&nbsp;- - - 
</td>
<td> 7 
</td>
<td> o 904SAB4 
</td>
<td> 3 
</td>
<td> &nbsp;&nbsp;- - - 
</td>
</tr>
</table>
</blockquote>
<blockquote>
<p>
                Stick Relays (No Engine Return, No Fleeting)
</p>
<blockquote>
<p></p>
<table border="1">
<tr><th align="left" colspan="3"><p>&nbsp;</p>
<p>&nbsp;&nbsp;Route <b>LOOP-YL-DT-R</b> Aspect DIVERGING_RESTRICTING  - Reverse Loop to Departure Track via Yard ladder - DAT is occupied</p>
<p>&nbsp;</p></th></tr>
                        <!-- table border="1" -->
<tr><th>Switches</th><th>Tracks</th><th>Signals</th></tr>
<tr><td>
<code>CP_Watsonville_S:901&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::REVERSE</code><BR>
<code>CP_Watsonville_S:903&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:905&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:907&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:909&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
</td><td>
<code>CP_Watsonville_S:901T1&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:YLAD&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
</td><td>
<code>CP_Watsonville_S:902&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::LEFT</code><BR>
<code>CP_Watsonville_S:904&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::LEFT</code><BR>
</td></tr><!-- /table -->
<p></p>
<tr><th align="left" colspan="3"><p>&nbsp;</p>
<p>&nbsp;&nbsp;Route <b>LOOP-YL-DT</b> Aspect DIVERGING_CLEAR  - Reverse Loop to Departure Track via Yard ladder</p>
<p>&nbsp;</p></th></tr>
                        <!-- table border="1" -->
<tr><th>Switches</th><th>Tracks</th><th>Signals</th></tr>
<tr><td>
<code>CP_Watsonville_S:901&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::REVERSE</code><BR>
<code>CP_Watsonville_S:903&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:905&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:907&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:909&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
</td><td>
<code>CP_Watsonville_S:901T1&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:DAT&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:YLAD&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
</td><td>
<code>CP_Watsonville_S:902&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::LEFT</code><BR>
<code>CP_Watsonville_S:904&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::LEFT</code><BR>
</td></tr><!-- /table -->
<p></p>
<tr><th align="left" colspan="3"><p>&nbsp;</p>
<p>&nbsp;&nbsp;Route <b>LOOP-YL-YT1</b> Aspect DIVERGING_APPROACH  - Reverse Loop to Yard Track 1</p>
<p>&nbsp;</p></th></tr>
                        <!-- table border="1" -->
<tr><th>Switches</th><th>Tracks</th><th>Signals</th></tr>
<tr><td>
<code>CP_Watsonville_S:903&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::REVERSE</code><BR>
<code>CP_Watsonville_S:905&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:907&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:909&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
</td><td>
<code>CP_Watsonville_S:903T2&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:1SAT&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:YLAD&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
</td><td>
<code>CP_Watsonville_S:902&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::LEFT</code><BR>
</td></tr><!-- /table -->
<p></p>
<tr><th align="left" colspan="3"><p>&nbsp;</p>
<p>&nbsp;&nbsp;Route <b>LOOP-YL-YT2</b> Aspect DIVERGING_APPROACH  - Reverse Loop to Yard Track 2</p>
<p>&nbsp;</p></th></tr>
                        <!-- table border="1" -->
<tr><th>Switches</th><th>Tracks</th><th>Signals</th></tr>
<tr><td>
<code>CP_Watsonville_S:905&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::REVERSE</code><BR>
<code>CP_Watsonville_S:907&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:909&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
</td><td>
<code>CP_Watsonville_S:905T2&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:2SAT&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:YLAD&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
</td><td>
<code>CP_Watsonville_S:902&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::LEFT</code><BR>
</td></tr><!-- /table -->
<p></p>
<tr><th align="left" colspan="3"><p>&nbsp;</p>
<p>&nbsp;&nbsp;Route <b>LOOP-YL-YT3</b> Aspect DIVERGING_APPROACH  - Reverse Loop to Yard Track 3</p>
<p>&nbsp;</p></th></tr>
                        <!-- table border="1" -->
<tr><th>Switches</th><th>Tracks</th><th>Signals</th></tr>
<tr><td>
<code>CP_Watsonville_S:907&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::REVERSE</code><BR>
<code>CP_Watsonville_S:909&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
</td><td>
<code>CP_Watsonville_S:907T2&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:3SAT&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:YLAD&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
</td><td>
<code>CP_Watsonville_S:902&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::LEFT</code><BR>
</td></tr><!-- /table -->
<p></p>
<tr><th align="left" colspan="3"><p>&nbsp;</p>
<p>&nbsp;&nbsp;Route <b>LOOP-YL-YT4</b> Aspect DIVERGING_APPROACH  - Reverse Loop to Yard Track 4</p>
<p>&nbsp;</p></th></tr>
                        <!-- table border="1" -->
<tr><th>Switches</th><th>Tracks</th><th>Signals</th></tr>
<tr><td>
<code>CP_Watsonville_S:909&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::REVERSE</code><BR>
</td><td>
<code>CP_Watsonville_S:909T2&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:4SAT&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:YLAD&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
</td><td>
<code>CP_Watsonville_S:902&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::LEFT</code><BR>
</td></tr><!-- /table -->
<p></p>
</table>
</blockquote>
<p>&nbsp;</p>
<blockquote>
<p></p>
<table border="1">
<tr><th align="left" colspan="3"><p>&nbsp;</p>
<p>&nbsp;&nbsp;Route <b>Y1-LOOP</b> Aspect APPROACH  - Y1 to LOOP</p>
<p>&nbsp;</p></th></tr>
                        <!-- table border="1" -->
<tr><th>Switches</th><th>Tracks</th><th>Signals</th></tr>
<tr><td>
<code>CP_Watsonville_S:903&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::REVERSE</code><BR>
<code>CP_Watsonville_S:905&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:907&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:909&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
</td><td>
<code>CP_Watsonville_S:LOOP&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:YLAD&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
</td><td>
<code>CP_Watsonville_S:902&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::RIGHT&nbsp;</code><BR>
</td></tr><!-- /table -->
<p></p>
</table>
</blockquote>
<p>&nbsp;</p>
<blockquote>
<p></p>
<table border="1">
<tr><th align="left" colspan="3"><p>&nbsp;</p>
<p>&nbsp;&nbsp;Route <b>Y2-LOOP</b> Aspect APPROACH  - Y2 to LOOP</p>
<p>&nbsp;</p></th></tr>
                        <!-- table border="1" -->
<tr><th>Switches</th><th>Tracks</th><th>Signals</th></tr>
<tr><td>
<code>CP_Watsonville_S:905&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::REVERSE</code><BR>
<code>CP_Watsonville_S:907&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:909&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
</td><td>
<code>CP_Watsonville_S:LOOP&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:YLAD&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
</td><td>
<code>CP_Watsonville_S:902&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::RIGHT&nbsp;</code><BR>
</td></tr><!-- /table -->
<p></p>
</table>
</blockquote>
<p>&nbsp;</p>
<blockquote>
<p></p>
<table border="1">
<tr><th align="left" colspan="3"><p>&nbsp;</p>
<p>&nbsp;&nbsp;Route <b>Y3-LOOP</b> Aspect APPROACH  - Y3 to LOOP</p>
<p>&nbsp;</p></th></tr>
                        <!-- table border="1" -->
<tr><th>Switches</th><th>Tracks</th><th>Signals</th></tr>
<tr><td>
<code>CP_Watsonville_S:907&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::REVERSE</code><BR>
<code>CP_Watsonville_S:909&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
</td><td>
<code>CP_Watsonville_S:LOOP&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:YLAD&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
</td><td>
<code>CP_Watsonville_S:902&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::RIGHT&nbsp;</code><BR>
</td></tr><!-- /table -->
<p></p>
</table>
</blockquote>
<p>&nbsp;</p>
<blockquote>
<p></p>
<table border="1">
<tr><th align="left" colspan="3"><p>&nbsp;</p>
<p>&nbsp;&nbsp;Route <b>Y4-LOOP</b> Aspect APPROACH  - Y4 to LOOP</p>
<p>&nbsp;</p></th></tr>
                        <!-- table border="1" -->
<tr><th>Switches</th><th>Tracks</th><th>Signals</th></tr>
<tr><td>
<code>CP_Watsonville_S:909&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::REVERSE</code><BR>
</td><td>
<code>CP_Watsonville_S:LOOP&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:YLAD&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
</td><td>
<code>CP_Watsonville_S:902&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::RIGHT&nbsp;</code><BR>
</td></tr><!-- /table -->
<p></p>
</table>
</blockquote>
<p>&nbsp;</p>
<p>
                Stick Relays (No Engine Return, No Fleeting)
</p>
<blockquote>
<p></p>
<table border="1">
<tr><th align="left" colspan="3"><p>&nbsp;</p>
<p>&nbsp;&nbsp;Route <b>LOOP-DT</b> Aspect CLEAR  - Reverse Loop to Departure Track (usual route)</p>
<p>&nbsp;</p></th></tr>
                        <!-- table border="1" -->
<tr><th>Switches</th><th>Tracks</th><th>Signals</th></tr>
<tr><td>
<code>CP_Watsonville_S:901&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
</td><td>
<code>CP_Watsonville_S:901T1&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:DAT&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
</td><td>
<code>CP_Watsonville_S:904&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::LEFT</code><BR>
</td></tr><!-- /table -->
<p></p>
</table>
</blockquote>
<p>&nbsp;</p>
<blockquote>
<p></p>
<table border="1">
<tr><th align="left" colspan="3"><p>&nbsp;</p>
<p>&nbsp;&nbsp;Route <b>RDT-LOOP</b> Aspect RESTRICTING  - Southbound (reverse running) direct to Reverse Loop</p>
<p>&nbsp;</p></th></tr>
                        <!-- table border="1" -->
<tr><th>Switches</th><th>Tracks</th><th>Signals</th></tr>
<tr><td>
<code>CP_Watsonville_S:901&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
</td><td>
<code>CP_Watsonville_S:901T1&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:LOOP&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
</td><td>
<code>CP_Watsonville_S:904&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::RIGHT&nbsp;</code><BR>
</td></tr><!-- /table -->
<p></p>
<tr><th align="left" colspan="3"><p>&nbsp;</p>
<p>&nbsp;&nbsp;Route <b>RDT-Y-LOOP</b> Aspect DIVERGING_RESTRICTING  - Southbound (reverse running) to Reverse Loop via Yard Ladder</p>
<p>&nbsp;</p></th></tr>
                        <!-- table border="1" -->
<tr><th>Switches</th><th>Tracks</th><th>Signals</th></tr>
<tr><td>
<code>CP_Watsonville_S:901&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::REVERSE</code><BR>
<code>CP_Watsonville_S:903&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:905&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:907&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
<code>CP_Watsonville_S:909&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SwitchDevice::NORMAL</code><BR>
</td><td>
<code>CP_Watsonville_S:901T1&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:LOOP&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
<code>CP_Watsonville_S:YLAD&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TrackCircuitDevice::UNOCCUPIED</code><BR>
</td><td>
<code>CP_Watsonville_S:902&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::RIGHT&nbsp;</code><BR>
<code>CP_Watsonville_S:904&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SignalDevice::RIGHT&nbsp;</code><BR>
</td></tr><!-- /table -->
<p></p>
</table>
</blockquote>
<p>&nbsp;</p>
</blockquote>

<pre>
Sketch uses 826074 bytes (63%) of program storage space. Maximum is 1310720 bytes.
Global variables use 46924 bytes (14%) of dynamic memory, leaving 280756 bytes for local variables. Maximum is 327680 bytes.

</pre>

## CP_Watsonville_South SOURCE 

~~~ cpp
//FQBN:esp32:esp32:esp32doit-devkit-v1
//PORT:NODE_CP_WATSONVILLE_S
//
// Field Unit Node Template
// SPCoast: John Plocher, August, 2020
//
#include <Wire.h>
#include <elapsedMillis.h>
#include <I2Cexpander.h>
#include <MaintainerDisplay.h>
#include <SimpleHashTable.h>
#include <CodeLineMQTT.h>
#include <FieldUnit.h>
/*
 *     Autogenerated Control Point code for
 *     ************************************
 *        CP_Watsonville_S Field Unit    
 *     ************************************
 *     on: 2021-04-11 17:41
 * 
 *     South end of Watsonville Staging Yard.  MP 90
 * 
 *     Yard ladder, reverse loop and departure track.  See also Watsonville North.
 * 
 *     < Railroad West/North                             Railroad East/South >
 *                                                        O-| 904Na
 *     Departure <================DAT= ==== 1T1========+==== =========================\
 *                                     |-OO 904Sab      \901                            \
 *                                                  903T2\                              |
 *     Yard Track 1 >=========d==1SAT= ===d-3T2===========d\  YLAD                       |
 *                                     |-O 902sa         903\d-903T1                     |
 *     Yard Track 2 >=========d==2SAT= ===d 5T2=============d\                          ROCC (reverse LOOP)
 *                                     |-O 902sb           905\d                         |
 *     Yard Track 3 >=========d==3SAT= ===d 7T2===============d\                         |
 *                                     |-O 902sc             907\d                       |
 *     Yard Track 4 >=========d==4SAT= ===d 9T2=================d\  OO-| 902Nab         /
 *                                     |-O 902sd               909\=d= ===============/
 *                            ^    [MC]   ^                    ^
 *                           IR           IR                  IR  ('d' = IR Detectors)
 * 
 *     This 'CP' is all within yard limits of Watsonville Staging Yard.
 *     There is a MCall for departing trains to contact the dispatcher for authority.
 * 
 *     Trains on a Yard Track exit "Southbound", traverse the reverse loop to become "Northbound"
 *     and exit via the departure track and Watsonville North.
 * 
 *     Dwarf Signals control the exit from each Yard Track.
 * 
 *     Optical sensors ('d') are used for Switch Occupancy and Yard Track stopping
 *     position and switch fouling detection
 *     YLAD = Block detector plus 4x IR (point fouling) + 4x (yard fouling) IR detectors
 *     YARDx = Block detector + IR detector   IR detector is used to indicate where to stop a train
 * 
 *     There are 5 switches in CP Watsonville South:
 *         SW1 for the reverse loop Departure track (usually left Normal)
 *         SW3 ... SW9 for the Yard Track exit ladder
 *     Switches are Power Routing, so Turtle does not power frog...
 *     Sw 3,5,7, and 9 are all part of the same block detection block
 * 
 *     There are 2 Signals that control traffic - 2 (Yard Track access) and 4 (Departure track access)
 * 
 *      Southbound Approach on Departure Track:  DAT
 *      Southbound Approach on Yard Track:  [1-4]SAT
 *      Northbound Approach from LOOP: LOOP
 * 
 *     Possible routes:
 *         (A) Normal Operations NX:  eNter from Yard_n, exit on DT
 *             Leave Yard from ____________ via LOOP and Departure Track
 *                         Yard Track 1
 *                         Yard Track 2
 *                         Yard Track 3
 *                         Yard Track 4
 * 
 *             Set switches as desired, S2 RIGHT, S4 LEFT,FLEET
 * 
 *         (B) Infrequent, used during layout operations setup: eNter from DT, exit on Yard_n
 *             Enter ____________ from Departure track and LOOP
 *               Yard Track 1
 *               Yard Track 2
 *               Yard Track 3
 *               Yard Track 4
 * 
 *             Set switches as desired, S2 LEFT, S4 RIGHT,FLEET
 * 
 *         (C) Turn Train from Departure track and LOOP back out through Departure Track
 * 
 *             Set all switches Normal, S4 RIGHT.
 *             When train is in LOOP and 1T1 UNOCCUPIED, set SW1 Reverse, S4 STOP, then S4 LEFT
 * 
 * 
 * 
 *           Indications for CP_Watsonville_S
 *           +---------+---------+---------+---------+---------+---------+---------+---------+
 *           | bit 0   | bit 1   | bit 2   | bit 3   | bit 4   | bit 5   | bit 6   | bit 7   |
 *           +---------+---------+---------+---------+---------+---------+---------+---------+
 *   Byte  0 | 901NWK  | 901RWK  | 903NWK  | 903RWK  | 905NWK  | 905RWK  | 907NWK  | 907RWK  |
 *   Byte  1 | 909NWK  | 909RWK  | 902SGK  | 902NGK  | 902TEK  | 904SGK  | 904NGK  | 904TEK  |
 *   Byte  2 | 901T1K  | 903T1K  | 905T1K  | 907T1K  | 909T1K  | 903T2K  | 905T2K  | 907T2K  |
 *   Byte  3 | 909T2K  | 903T3K  | 905T3K  | 907T3K  | 909T3K  | - - -   | - - -   | - - -   |
 *   Byte  4 | 1SATK   | 2SATK   | 3SATK   | 4SATK   | 1SAATK  | 2SAATK  | 3SAATK  | 4SAATK  |
 *   Byte  5 | - - -   | DATK    | YLADK   | - - -   | - - -   | - - -   | - - -   | MC1K    |
 *   Byte  6 | RSHORTK | RTONK   | ROCCK   | ROFFK   | BSHORTK | BTONK   | BOCCK   | BOFFK   |
 *           +---------+---------+---------+---------+---------+---------+---------+---------+
 * 
 *           Controls for CP_Watsonville_S
 *           +---------+---------+---------+---------+---------+---------+---------+---------+
 *           | bit 0   | bit 1   | bit 2   | bit 3   | bit 4   | bit 5   | bit 6   | bit 7   |
 *           +---------+---------+---------+---------+---------+---------+---------+---------+
 *   Byte  0 | 901NWS  | 901RWS  | 903NWS  | 903RWS  | 905NWS  | 905RWS  | 907NWS  | 907RWS  |
 *   Byte  1 | 909NWS  | 909RWS  | 902SGS  | 902NGS  | 902HS   | 904SGS  | 904NGS  | 904HS   |
 *   Byte  2 | RPONS   | RPOFFS  | BPONS   | BPOFFS  | - - -   | - - -   | - - -   | MC1S    |
 *           +---------+---------+---------+---------+---------+---------+---------+---------+
 * 
 * 
 * 
 *           Expanders for CP_Watsonville_S		   (1=input, 0=output)
 *           +-------------------------------------------------------------------------------+
 *   Dev  0  | MCP23017        	| I2C Address: 0	|  I/O Map: 0111011101110111         |
 *   Dev  1  | MCP23017        	| I2C Address: 1	|  I/O Map: 0000011101110111         |
 *   Dev  2  | MCP23017        	| I2C Address: 2	|  I/O Map: 1111111111111111         |
 *   Dev  3  | MCP23017        	| I2C Address: 3	|  I/O Map: 0000000000001111         |
 *   Dev  4  | MCP23017        	| I2C Address: 4	|  I/O Map: 0000000000000000         |
 *           +-------------------------------------------------------------------------------+
 * 
 *           Expanders for CP_Watsonville_S
 *           +----------------------+------+----------+------+----------+------+----------+------+----------+
 *           | Dev         I2C addr |  Bit |  Signal  |  Bit |  Signal  |  Bit |  Signal  |  Bit |  Signal  |
 *           +----------------------+------+----------+------+----------+------+----------+------+----------+
 *           | 0  MCP23017     0x00 |   0  | i 901NW  |   4  | i 903NW  |   8  | i 905NW  |   12 | i 907NW  |
 *           |                      |   1  | i 901RW  |   5  | i 903RW  |   9  | i 905RW  |   13 | i 907RW  |
 *           |                      |   2  | i 901T1  |   6  | i 903T1  |   10 | i 905T1  |   14 | i 907T1  |
 *           |                      |   3  | o T901   |   7  | o T903   |   11 | o T905   |   15 | o T907   |
 *           +----------------------+------+----------+------+----------+------+----------+------+----------+
 *           | Dev         I2C addr |  Bit |  Signal  |  Bit |  Signal  |  Bit |  Signal  |  Bit |  Signal  |
 *           +----------------------+------+----------+------+----------+------+----------+------+----------+
 *           | 1  MCP23017     0x01 |   0  | i 909NW  |   4  | i RSHORT |   8  | i BSHORT |   12 | o MC1    |
 *           |                      |   1  | i 909RW  |   5  | i RTON   |   9  | i BTON   |   13 | o XO11   |
 *           |                      |   2  | i 909T1  |   6  | i ROCC   |   10 | i BOCC   |   14 | o XO12   |
 *           |                      |   3  | o T909   |   7  | o ROFF   |   11 | o BOFF   |   15 | o XO13   |
 *           +----------------------+------+----------+------+----------+------+----------+------+----------+
 *           | Dev         I2C addr |  Bit |  Signal  |  Bit |  Signal  |  Bit |  Signal  |  Bit |  Signal  |
 *           +----------------------+------+----------+------+----------+------+----------+------+----------+
 *           | 2  MCP23017     0x02 |   0  | i YLT    |   4  | i 903T2  |   8  | i 903T3  |   12 | i 1SAT   |
 *           |                      |   1  | i DAT    |   5  | i 905T2  |   9  | i 905T3  |   13 | i 2SAT   |
 *           |                      |   2  | i XI22   |   6  | i 907T2  |   10 | i 907T3  |   14 | i 3SAT   |
 *           |                      |   3  | i XI23   |   7  | i 909T2  |   11 | i 909T3  |   15 | i 4SAT   |
 *           +----------------------+------+----------+------+----------+------+----------+------+----------+
 *           | Dev         I2C addr |  Bit |  Signal  |  Bit |  Signal  |  Bit |  Signal  |  Bit |  Signal  |
 *           +----------------------+------+----------+------+----------+------+----------+------+----------+
 *           | 3  MCP23017     0x03 |   0  | i 1SAAT  |   4  | o 902NAB1|   8  | o 902SA1 |   12 | o 902SC1 |
 *           |                      |   1  | i 2SAAT  |   5  | o 902NAB2|   9  | o 902SA2 |   13 | o 902SC2 |
 *           |                      |   2  | i 3SAAT  |   6  | o 902NAB3|   10 | o 902SB1 |   14 | o 902SD1 |
 *           |                      |   3  | i 4SAAT  |   7  | o 902NAB4|   11 | o 902SB2 |   15 | o 902SD2 |
 *           +----------------------+------+----------+------+----------+------+----------+------+----------+
 *           | Dev         I2C addr |  Bit |  Signal  |  Bit |  Signal  |  Bit |  Signal  |  Bit |  Signal  |
 *           +----------------------+------+----------+------+----------+------+----------+------+----------+
 *           | 4  MCP23017     0x04 |   0  | o 904NA1 |   4  | o 904SAB1|   8  | - - -    |   12 | - - -    |
 *           |                      |   1  | o 904NA2 |   5  | o 904SAB2|   9  | - - -    |   13 | - - -    |
 *           |                      |   2  | - - -    |   6  | o 904SAB3|   10 | - - -    |   14 | - - -    |
 *           |                      |   3  | - - -    |   7  | o 904SAB4|   11 | - - -    |   15 | - - -    |
 *           +----------------------+------+----------+------+----------+------+----------+------+----------+
 * 
 * 
 */
#define NODE_CTC                                0x0069
#define NODE_CP_WATSONVILLE_S              	0x0090
#define NODE_ME                            	NODE_CP_WATSONVILLE_S
// event triggers for loop()
elapsedMillis displayTime;
#define DELAY_DISPLAY   (500)     // between OLED screen updates
elapsedMillis checkTime;
#define DELAY_CHECK     (100)     // between Field checks
elapsedMillis otaTime;
#define DELAY_OTA       ( 75)     // between OTA updates
#define CP_WATSONVILLE_S_PORTS             	5
enum Expanders {
    E0, // Expander: cp: CP_Watsonville_S field: fieldunit name: 0 dev: 0  bit: 16 suffix: _E: type: MCP23017     init: 0111011101110111 size: 16      
    E1, // Expander: cp: CP_Watsonville_S field: fieldunit name: 1 dev: 1  bit: 16 suffix: _E: type: MCP23017     init: 0000011101110111 size: 16      
    E2, // Expander: cp: CP_Watsonville_S field: fieldunit name: 2 dev: 2  bit: 16 suffix: _E: type: MCP23017     init: 1111111111111111 size: 16      
    E3, // Expander: cp: CP_Watsonville_S field: fieldunit name: 3 dev: 3  bit: 16 suffix: _E: type: MCP23017     init: 0000000000001111 size: 16      
    E4, // Expander: cp: CP_Watsonville_S field: fieldunit name: 4 dev: 4  bit: 16 suffix: _E: type: MCP23017     init: 0000000000000000 size: 16      
NUMEXPANDERS };
Adafruit_SSD1306 display(128, 64);   // OLED_SCREEN_WIDTH, OLED_SCREEN_HEIGHT
// ---------------------------------------------
//        Per ControlPoint identity
// ---------------------------------------------
const char *myLayoutName   = "spcoast";               // Many layouts can share this same MQTT topic namespace
const char* myHostname     = "CP_Watsonville_S";      // For OTA updates
// Network Configuration - these values must match your local network
const byte *myIPAddress    = NULL;                    // if NULL, use DHCP, else assign this as node's static IP address
const byte  myGW[]         = { 192,168,1,    1 };     // Gateway/router to use if not using DHCP
const byte  myNMASK[]      = { 255,255,255,  0 };     // ... and subnet mask
const char *mySSID         = "SPCoast";               // WiFi: modify to match your environment
const char *myWEP          = "railroad";              // WiFi: ...case matters!
const char *myMQTTServer   = "192.168.1.40";          // Your local mqtt server IP Address
// ---------------------------------------------
CodeLine          *codeline;
I2CMatrix         *matrix;
FieldIO           *fIO;
MaintainerDisplay *md;
FieldUnit         *fieldUnit      = NULL;
extern byte        matrix_font[128][8];
// ---------------------------------------------
//
// Controls                                     ID(byte, bit)
//
#define CP_Watsonville_S_901NWS            	ID(0, 0)
#define CP_Watsonville_S_901RWS            	ID(0, 1)
#define CP_Watsonville_S_903NWS            	ID(0, 2)
#define CP_Watsonville_S_903RWS            	ID(0, 3)
#define CP_Watsonville_S_905NWS            	ID(0, 4)
#define CP_Watsonville_S_905RWS            	ID(0, 5)
#define CP_Watsonville_S_907NWS            	ID(0, 6)
#define CP_Watsonville_S_907RWS            	ID(0, 7)
#define CP_Watsonville_S_909NWS            	ID(1, 0)
#define CP_Watsonville_S_909RWS            	ID(1, 1)
#define CP_Watsonville_S_902SGS            	ID(1, 2)
#define CP_Watsonville_S_902NGS            	ID(1, 3)
#define CP_Watsonville_S_902HS             	ID(1, 4)
#define CP_Watsonville_S_904SGS            	ID(1, 5)
#define CP_Watsonville_S_904NGS            	ID(1, 6)
#define CP_Watsonville_S_904HS             	ID(1, 7)
#define CP_Watsonville_S_RPONS             	ID(2, 0)
#define CP_Watsonville_S_RPOFFS            	ID(2, 1)
#define CP_Watsonville_S_BPONS             	ID(2, 2)
#define CP_Watsonville_S_BPOFFS            	ID(2, 3)
#define CP_Watsonville_S_MC1S              	ID(2, 7)
//
// Indications                                  ID(byte, bit)
//
#define CP_Watsonville_S_901NWK            	ID(0, 0)
#define CP_Watsonville_S_901RWK            	ID(0, 1)
#define CP_Watsonville_S_903NWK            	ID(0, 2)
#define CP_Watsonville_S_903RWK            	ID(0, 3)
#define CP_Watsonville_S_905NWK            	ID(0, 4)
#define CP_Watsonville_S_905RWK            	ID(0, 5)
#define CP_Watsonville_S_907NWK            	ID(0, 6)
#define CP_Watsonville_S_907RWK            	ID(0, 7)
#define CP_Watsonville_S_909NWK            	ID(1, 0)
#define CP_Watsonville_S_909RWK            	ID(1, 1)
#define CP_Watsonville_S_902SGK            	ID(1, 2)
#define CP_Watsonville_S_902NGK            	ID(1, 3)
#define CP_Watsonville_S_902TEK            	ID(1, 4)
#define CP_Watsonville_S_904SGK            	ID(1, 5)
#define CP_Watsonville_S_904NGK            	ID(1, 6)
#define CP_Watsonville_S_904TEK            	ID(1, 7)
#define CP_Watsonville_S_901T1K            	ID(2, 0)
#define CP_Watsonville_S_903T1K            	ID(2, 1)
#define CP_Watsonville_S_905T1K            	ID(2, 2)
#define CP_Watsonville_S_907T1K            	ID(2, 3)
#define CP_Watsonville_S_909T1K            	ID(2, 4)
#define CP_Watsonville_S_903T2K            	ID(2, 5)
#define CP_Watsonville_S_905T2K            	ID(2, 6)
#define CP_Watsonville_S_907T2K            	ID(2, 7)
#define CP_Watsonville_S_909T2K            	ID(3, 0)
#define CP_Watsonville_S_903T3K            	ID(3, 1)
#define CP_Watsonville_S_905T3K            	ID(3, 2)
#define CP_Watsonville_S_907T3K            	ID(3, 3)
#define CP_Watsonville_S_909T3K            	ID(3, 4)
#define CP_Watsonville_S_1SATK             	ID(4, 0)
#define CP_Watsonville_S_2SATK             	ID(4, 1)
#define CP_Watsonville_S_3SATK             	ID(4, 2)
#define CP_Watsonville_S_4SATK             	ID(4, 3)
#define CP_Watsonville_S_1SAATK            	ID(4, 4)
#define CP_Watsonville_S_2SAATK            	ID(4, 5)
#define CP_Watsonville_S_3SAATK            	ID(4, 6)
#define CP_Watsonville_S_4SAATK            	ID(4, 7)
#define CP_Watsonville_S_DATK              	ID(5, 1)
#define CP_Watsonville_S_YLADK             	ID(5, 2)
#define CP_Watsonville_S_MC1K              	ID(5, 7)
#define CP_Watsonville_S_RSHORTK           	ID(6, 0)
#define CP_Watsonville_S_RTONK             	ID(6, 1)
#define CP_Watsonville_S_ROCCK             	ID(6, 2)
#define CP_Watsonville_S_ROFFK             	ID(6, 3)
#define CP_Watsonville_S_BSHORTK           	ID(6, 4)
#define CP_Watsonville_S_BTONK             	ID(6, 5)
#define CP_Watsonville_S_BOCCK             	ID(6, 6)
#define CP_Watsonville_S_BOFFK             	ID(6, 7)
//
// Field Unit                                   ID(expander, bit)
//
#define CP_Watsonville_S_901NWF            	ID(0, 0)
#define CP_Watsonville_S_901RWF            	ID(0, 1)
#define CP_Watsonville_S_901T1F            	ID(0, 2)
#define CP_Watsonville_S_T901F             	ID(0, 3)
#define CP_Watsonville_S_903NWF            	ID(0, 4)
#define CP_Watsonville_S_903RWF            	ID(0, 5)
#define CP_Watsonville_S_903T1F            	ID(0, 6)
#define CP_Watsonville_S_T903F             	ID(0, 7)
#define CP_Watsonville_S_905NWF            	ID(0, 8)
#define CP_Watsonville_S_905RWF            	ID(0, 9)
#define CP_Watsonville_S_905T1F            	ID(0, 10)
#define CP_Watsonville_S_T905F             	ID(0, 11)
#define CP_Watsonville_S_907NWF            	ID(0, 12)
#define CP_Watsonville_S_907RWF            	ID(0, 13)
#define CP_Watsonville_S_907T1F            	ID(0, 14)
#define CP_Watsonville_S_T907F             	ID(0, 15)
#define CP_Watsonville_S_909NWF            	ID(1, 0)
#define CP_Watsonville_S_909RWF            	ID(1, 1)
#define CP_Watsonville_S_909T1F            	ID(1, 2)
#define CP_Watsonville_S_T909F             	ID(1, 3)
#define CP_Watsonville_S_RSHORTF           	ID(1, 4)
#define CP_Watsonville_S_RTONF             	ID(1, 5)
#define CP_Watsonville_S_ROCCF             	ID(1, 6)
#define CP_Watsonville_S_ROFFF             	ID(1, 7)
#define CP_Watsonville_S_BSHORTF           	ID(1, 8)
#define CP_Watsonville_S_BTONF             	ID(1, 9)
#define CP_Watsonville_S_BOCCF             	ID(1, 10)
#define CP_Watsonville_S_BOFFF             	ID(1, 11)
#define CP_Watsonville_S_YLTF              	ID(2, 0)
#define CP_Watsonville_S_DATF              	ID(2, 1)
#define CP_Watsonville_S_XI22F             	ID(2, 2)
#define CP_Watsonville_S_XI23F             	ID(2, 3)
#define CP_Watsonville_S_903T2F            	ID(2, 4)
#define CP_Watsonville_S_905T2F            	ID(2, 5)
#define CP_Watsonville_S_907T2F            	ID(2, 6)
#define CP_Watsonville_S_909T2F            	ID(2, 7)
#define CP_Watsonville_S_903T3F            	ID(2, 8)
#define CP_Watsonville_S_905T3F            	ID(2, 9)
#define CP_Watsonville_S_907T3F            	ID(2, 10)
#define CP_Watsonville_S_909T3F            	ID(2, 11)
#define CP_Watsonville_S_1SATF             	ID(2, 12)
#define CP_Watsonville_S_2SATF             	ID(2, 13)
#define CP_Watsonville_S_3SATF             	ID(2, 14)
#define CP_Watsonville_S_4SATF             	ID(2, 15)
#define CP_Watsonville_S_1SAATF            	ID(3, 0)
#define CP_Watsonville_S_2SAATF            	ID(3, 1)
#define CP_Watsonville_S_3SAATF            	ID(3, 2)
#define CP_Watsonville_S_4SAATF            	ID(3, 3)
#define CP_Watsonville_S_MC1F              	ID(1, 12)
#define CP_Watsonville_S_XO11F             	ID(1, 13)
#define CP_Watsonville_S_XO12F             	ID(1, 14)
#define CP_Watsonville_S_XO13F             	ID(1, 15)
#define CP_Watsonville_S_902NAB1F          	ID(3, 4)
#define CP_Watsonville_S_902NAB2F          	ID(3, 5)
#define CP_Watsonville_S_902NAB3F          	ID(3, 6)
#define CP_Watsonville_S_902NAB4F          	ID(3, 7)
#define CP_Watsonville_S_902SA1F           	ID(3, 8)
#define CP_Watsonville_S_902SA2F           	ID(3, 9)
#define CP_Watsonville_S_902SB1F           	ID(3, 10)
#define CP_Watsonville_S_902SB2F           	ID(3, 11)
#define CP_Watsonville_S_902SC1F           	ID(3, 12)
#define CP_Watsonville_S_902SC2F           	ID(3, 13)
#define CP_Watsonville_S_902SD1F           	ID(3, 14)
#define CP_Watsonville_S_902SD2F           	ID(3, 15)
#define CP_Watsonville_S_904NA1F           	ID(4, 0)
#define CP_Watsonville_S_904NA2F           	ID(4, 1)
#define CP_Watsonville_S_904SAB1F          	ID(4, 4)
#define CP_Watsonville_S_904SAB2F          	ID(4, 5)
#define CP_Watsonville_S_904SAB3F          	ID(4, 6)
#define CP_Watsonville_S_904SAB4F          	ID(4, 7)
// ---------------------------------------------   MQTT handlers
bool handleIndications(CodeLine *cl, Indications *indication) {
    if (fieldUnit) {
        return fieldUnit->handleIndications(indication);
    }
    return false;
}

bool handleControls(CodeLine *cl, Controls *control) {
    if (fieldUnit) {
        return fieldUnit->handleControls(control);
    }
    return false;
}

void setup(void) {
    unsigned long int startmem = ESP.getFreeHeap(), finishmem;
    Serial.begin(115200);
    while (!Serial) {
      ; // wait for serial port to connect. Needed for Native USB
    }
    Serial.print("ControlPoint Firmware: ");
    Serial.print(myLayoutName);
    Serial.print(":");
    Serial.print(myHostname);
    if (myIPAddress) {
        Serial.print(" (");
        Serial.print(myIPAddress[0]);Serial.print(".");
        Serial.print(myIPAddress[1]);Serial.print(".");
        Serial.print(myIPAddress[2]);Serial.print(".");
        Serial.print(myIPAddress[3]);Serial.print(") ");
    }
    Serial.print(" Node 0x"); Serial.println(NODE_ME, HEX);
    Wire.begin(21,22);  // for ESP32-DEV
    matrix   = new I2CMatrix(0x01, 2);
    md       = new MaintainerDisplay();
    md->init(&display);
    codeline = new CodeLine(myHostname, myLayoutName,  myMQTTServer, mySSID, myWEP, myGW, myNMASK, NODE_ME, md, matrix, myIPAddress);
    codeline->update(MaintainerDisplay::REFRESH);    // update OLED with codeline state for debugging
    codeline->registerCHandler(handleControls);
    codeline->registerIHandler(handleIndications);
    // Field I/O abstraction - collection of all appliances in Field Unit
    fIO      = new FieldIO(NUMEXPANDERS);
    //        #   addr  type                   group 4           group 3           group 2           group 1
    fIO->init(E0, 0x00, I2Cexpander::MCP23017, FieldIO::TURTLE,  FieldIO::TURTLE,  FieldIO::TURTLE,  FieldIO::TURTLE);
    fIO->init(E1, 0x01, I2Cexpander::MCP23017, FieldIO::OUTPUTS, FieldIO::TURTLE,  FieldIO::TURTLE,  FieldIO::TURTLE);
    fIO->init(E2, 0x02, I2Cexpander::MCP23017, FieldIO::INPUTS , FieldIO::INPUTS , FieldIO::INPUTS , FieldIO::INPUTS );
    fIO->init(E3, 0x03, I2Cexpander::MCP23017, FieldIO::OUTPUTS, FieldIO::OUTPUTS, FieldIO::OUTPUTS, FieldIO::INPUTS );
    fIO->init(E4, 0x04, I2Cexpander::MCP23017, FieldIO::OUTPUTS, FieldIO::OUTPUTS, FieldIO::OUTPUTS, FieldIO::OUTPUTS);
    // Field Unit abstraction - all the subsystems used by the Field Unit
    fieldUnit = new FieldUnit(myHostname, myLayoutName, NODE_CP_WATSONVILLE_S, NODE_CTC, fIO, codeline);
    // Maintainer Call
    // On fascia, near Yard Ladder
    fieldUnit->add(new MaintainerCallDevice("CP_Watsonville_S:MC1",        NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_MC1S,    CP_Watsonville_S_MC1K,    CP_Watsonville_S_MC1F     ));
    // Track Power
    // DCC Booster
    // fieldUnit->add(new TrackPowerDevice("CP_Watsonville_S:B",          NODE_CP_WATSONVILLE_S,   
    //     /* controls       */             CP_Watsonville_S_BPONS,       CP_Watsonville_S_BPOFFS,
    //     /* indications    */             CP_Watsonville_S_BSHORT,      CP_Watsonville_S_BTONK,    CP_Watsonville_S_BOCCK,   CP_Watsonville_S_BOFFK,
    //     /* Track Circuit  */             CP_Watsonville_S_BSHORTF,     CP_Watsonville_S_BTONF,    CP_Watsonville_S_BOCCF,   CP_Watsonville_S_BOFFF);
    // Reverse Loop
    // fieldUnit->add(new TrackPowerDevice("CP_Watsonville_S:R",          NODE_CP_WATSONVILLE_S,   
    //     /* controls       */             CP_Watsonville_S_RPONS,       CP_Watsonville_S_RPOFFS,
    //     /* indications    */             CP_Watsonville_S_RSHORT,      CP_Watsonville_S_RTONK,    CP_Watsonville_S_ROCCK,   CP_Watsonville_S_ROFFK,
    //     /* Track Circuit  */             CP_Watsonville_S_RSHORTF,     CP_Watsonville_S_RTONF,    CP_Watsonville_S_ROCCF,   CP_Watsonville_S_ROFFF);
    // Track Circuits
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:1SAAT",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_1SAATK,  CP_Watsonville_S_1SAATF   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:1SAT",       NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_1SATK,   CP_Watsonville_S_1SATF    ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:2SAAT",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_2SAATK,  CP_Watsonville_S_2SAATF   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:2SAT",       NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_2SATK,   CP_Watsonville_S_2SATF    ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:3SAAT",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_3SAATK,  CP_Watsonville_S_3SAATF   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:3SAT",       NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_3SATK,   CP_Watsonville_S_3SATF    ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:4SAAT",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_4SAATK,  CP_Watsonville_S_4SAATF   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:4SAT",       NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_4SATK,   CP_Watsonville_S_4SATF    ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:901T1",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_901T1K,  CP_Watsonville_S_901T1F   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:903T1",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_903T1K,  CP_Watsonville_S_903T1F   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:903T2",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_903T2K,  CP_Watsonville_S_903T2F   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:903T3",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_903T3K,  CP_Watsonville_S_903T3F   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:905T1",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_905T1K,  CP_Watsonville_S_905T1F   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:905T2",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_905T2K,  CP_Watsonville_S_905T2F   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:905T3",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_905T3K,  CP_Watsonville_S_905T3F   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:907T1",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_907T1K,  CP_Watsonville_S_907T1F   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:907T2",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_907T2K,  CP_Watsonville_S_907T2F   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:907T3",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_907T3K,  CP_Watsonville_S_907T3F   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:909T1",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_909T1K,  CP_Watsonville_S_909T1F   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:909T2",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_909T2K,  CP_Watsonville_S_909T2F   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:909T3",      NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_909T3K,  CP_Watsonville_S_909T3F   ));
    fieldUnit->add(new TrackCircuitDevice(  "CP_Watsonville_S:DAT",        NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_DATK,    CP_Watsonville_S_DATF     ));
    // Sections
    // Yard Departure ladder
    SectionDevice *d = new SectionDevice(   "CP_Watsonville_S:YLAD",       NODE_CP_WATSONVILLE_S,    CP_Watsonville_S_YLADK    );
        d->add((TrackCircuitDevice*)fieldUnit->get( "CP_Watsonville_S:903T1" ));
        d->add((TrackCircuitDevice*)fieldUnit->get( "CP_Watsonville_S:903T2" ));
        d->add((TrackCircuitDevice*)fieldUnit->get( "CP_Watsonville_S:905T1" ));
        d->add((TrackCircuitDevice*)fieldUnit->get( "CP_Watsonville_S:905T2" ));
        d->add((TrackCircuitDevice*)fieldUnit->get( "CP_Watsonville_S:907T1" ));
        d->add((TrackCircuitDevice*)fieldUnit->get( "CP_Watsonville_S:907T2" ));
        d->add((TrackCircuitDevice*)fieldUnit->get( "CP_Watsonville_S:909T1" ));
        d->add((TrackCircuitDevice*)fieldUnit->get( "CP_Watsonville_S:909T2" ));
    fieldUnit->add(d);
    // Switches
    fieldUnit->add(new SwitchDevice("CP_Watsonville_S:901", NODE_CP_WATSONVILLE_S,
        /* Track Circuit  */   (TrackCircuitDevice *)fieldUnit->get("CP_Watsonville_S:901T1"),
        /* controls       */   CP_Watsonville_S_901NWS, CP_Watsonville_S_901RWS,
        /* indications    */   CP_Watsonville_S_901NWK, CP_Watsonville_S_901RWK,
        /* fieldunit      */   CP_Watsonville_S_T901F, CP_Watsonville_S_901NWF, CP_Watsonville_S_901RWF));
    fieldUnit->add(new SwitchDevice("CP_Watsonville_S:903", NODE_CP_WATSONVILLE_S,
        /* Track Circuit  */   (TrackCircuitDevice *)fieldUnit->get("CP_Watsonville_S:YLAD"),
        /* controls       */   CP_Watsonville_S_903NWS, CP_Watsonville_S_903RWS,
        /* indications    */   CP_Watsonville_S_903NWK, CP_Watsonville_S_903RWK,
        /* fieldunit      */   CP_Watsonville_S_T903F, CP_Watsonville_S_903NWF, CP_Watsonville_S_903RWF));
    fieldUnit->add(new SwitchDevice("CP_Watsonville_S:905", NODE_CP_WATSONVILLE_S,
        /* Track Circuit  */   (TrackCircuitDevice *)fieldUnit->get("CP_Watsonville_S:YLAD"),
        /* controls       */   CP_Watsonville_S_905NWS, CP_Watsonville_S_905RWS,
        /* indications    */   CP_Watsonville_S_905NWK, CP_Watsonville_S_905RWK,
        /* fieldunit      */   CP_Watsonville_S_T905F, CP_Watsonville_S_905NWF, CP_Watsonville_S_905RWF));
    fieldUnit->add(new SwitchDevice("CP_Watsonville_S:907", NODE_CP_WATSONVILLE_S,
        /* Track Circuit  */   (TrackCircuitDevice *)fieldUnit->get("CP_Watsonville_S:YLAD"),
        /* controls       */   CP_Watsonville_S_907NWS, CP_Watsonville_S_907RWS,
        /* indications    */   CP_Watsonville_S_907NWK, CP_Watsonville_S_907RWK,
        /* fieldunit      */   CP_Watsonville_S_T907F, CP_Watsonville_S_907NWF, CP_Watsonville_S_907RWF));
    fieldUnit->add(new SwitchDevice("CP_Watsonville_S:909", NODE_CP_WATSONVILLE_S,
        /* Track Circuit  */   (TrackCircuitDevice *)fieldUnit->get("CP_Watsonville_S:YLAD"),
        /* controls       */   CP_Watsonville_S_909NWS, CP_Watsonville_S_909RWS,
        /* indications    */   CP_Watsonville_S_909NWK, CP_Watsonville_S_909RWK,
        /* fieldunit      */   CP_Watsonville_S_T909F, CP_Watsonville_S_909NWF, CP_Watsonville_S_909RWF));
    // Signals
    fieldUnit->add(new SignalDevice("CP_Watsonville_S:902", NODE_CP_WATSONVILLE_S,
        /* controls        */  CP_Watsonville_S_902NGS, CP_Watsonville_S_902SGS, CP_Watsonville_S_902HS,      // L, R, Stop
        /* indications     */  CP_Watsonville_S_902NGK, CP_Watsonville_S_902SGK, CP_Watsonville_S_902TEK));   // L, R, TimeElement
    fieldUnit->add(new SignalDevice("CP_Watsonville_S:904", NODE_CP_WATSONVILLE_S,
        /* controls        */  CP_Watsonville_S_904NGS, CP_Watsonville_S_904SGS, CP_Watsonville_S_904HS,      // L, R, Stop
        /* indications     */  CP_Watsonville_S_904NGK, CP_Watsonville_S_904SGK, CP_Watsonville_S_904TEK));   // L, R, TimeElement
    SignalDevice *s = NULL;
    SignalMast *mast = NULL;
            // ===================================================================
            // CP_Watsonville_S Signal 902: Loop to/from Yard Tracks
            // ===================================================================
            s = (SignalDevice *)fieldUnit->get("CP_Watsonville_S:902");
                // --------------------------------------------------------------
                // CP_Watsonville_S:902NAB Reverse Running on Reverse Loop entering Yard Ladder ...
                // --------------------------------------------------------------
                //
                mast = new SignalHead_2HeadColorLight("CP_Watsonville_S:902NAB", CP_Watsonville_S_902NAB1F, CP_Watsonville_S_902NAB2F, CP_Watsonville_S_902NAB3F, CP_Watsonville_S_902NAB4F );
                s->addHead(mast);
                    // --------------------------------------------------------------
                    // Route "LOOP-YL-DT-R" Reverse Loop to Departure Track via Yard ladder - DAT is occupied
                    // --------------------------------------------------------------
                    mast->createRoute("LOOP-YL-DT-R", Aspects::DIVERGING_RESTRICTING);
                    mast->addRouteDependency("LOOP-YL-DT-R", fieldUnit->get("CP_Watsonville_S:901T1"),     TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-DT-R", fieldUnit->get("CP_Watsonville_S:YLAD"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-DT-R", fieldUnit->get("CP_Watsonville_S:901"),       SwitchDevice::REVERSE);
                    mast->addRouteDependency("LOOP-YL-DT-R", fieldUnit->get("CP_Watsonville_S:903"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-DT-R", fieldUnit->get("CP_Watsonville_S:905"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-DT-R", fieldUnit->get("CP_Watsonville_S:907"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-DT-R", fieldUnit->get("CP_Watsonville_S:909"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-DT-R", fieldUnit->get("CP_Watsonville_S:902"),       SignalDevice::LEFT);
                    mast->addRouteDependency("LOOP-YL-DT-R", fieldUnit->get("CP_Watsonville_S:904"),       SignalDevice::LEFT);
                    // --------------------------------------------------------------
                    // Route "LOOP-YL-DT" Reverse Loop to Departure Track via Yard ladder
                    // --------------------------------------------------------------
                    mast->createRoute("LOOP-YL-DT",   Aspects::DIVERGING_CLEAR);
                    mast->addRouteDependency("LOOP-YL-DT",   fieldUnit->get("CP_Watsonville_S:901T1"),     TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-DT",   fieldUnit->get("CP_Watsonville_S:DAT"),       TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-DT",   fieldUnit->get("CP_Watsonville_S:YLAD"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-DT",   fieldUnit->get("CP_Watsonville_S:901"),       SwitchDevice::REVERSE);
                    mast->addRouteDependency("LOOP-YL-DT",   fieldUnit->get("CP_Watsonville_S:903"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-DT",   fieldUnit->get("CP_Watsonville_S:905"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-DT",   fieldUnit->get("CP_Watsonville_S:907"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-DT",   fieldUnit->get("CP_Watsonville_S:909"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-DT",   fieldUnit->get("CP_Watsonville_S:902"),       SignalDevice::LEFT);
                    mast->addRouteDependency("LOOP-YL-DT",   fieldUnit->get("CP_Watsonville_S:904"),       SignalDevice::LEFT);
                    // --------------------------------------------------------------
                    // Route "LOOP-YL-YT1" Reverse Loop to Yard Track 1
                    // --------------------------------------------------------------
                    mast->createRoute("LOOP-YL-YT1",  Aspects::DIVERGING_APPROACH);
                    mast->addRouteDependency("LOOP-YL-YT1",  fieldUnit->get("CP_Watsonville_S:903T2"),     TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-YT1",  fieldUnit->get("CP_Watsonville_S:1SAT"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-YT1",  fieldUnit->get("CP_Watsonville_S:YLAD"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-YT1",  fieldUnit->get("CP_Watsonville_S:903"),       SwitchDevice::REVERSE);
                    mast->addRouteDependency("LOOP-YL-YT1",  fieldUnit->get("CP_Watsonville_S:905"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-YT1",  fieldUnit->get("CP_Watsonville_S:907"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-YT1",  fieldUnit->get("CP_Watsonville_S:909"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-YT1",  fieldUnit->get("CP_Watsonville_S:902"),       SignalDevice::LEFT);
                    // --------------------------------------------------------------
                    // Route "LOOP-YL-YT2" Reverse Loop to Yard Track 2
                    // --------------------------------------------------------------
                    mast->createRoute("LOOP-YL-YT2",  Aspects::DIVERGING_APPROACH);
                    mast->addRouteDependency("LOOP-YL-YT2",  fieldUnit->get("CP_Watsonville_S:905T2"),     TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-YT2",  fieldUnit->get("CP_Watsonville_S:2SAT"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-YT2",  fieldUnit->get("CP_Watsonville_S:YLAD"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-YT2",  fieldUnit->get("CP_Watsonville_S:905"),       SwitchDevice::REVERSE);
                    mast->addRouteDependency("LOOP-YL-YT2",  fieldUnit->get("CP_Watsonville_S:907"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-YT2",  fieldUnit->get("CP_Watsonville_S:909"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-YT2",  fieldUnit->get("CP_Watsonville_S:902"),       SignalDevice::LEFT);
                    // --------------------------------------------------------------
                    // Route "LOOP-YL-YT3" Reverse Loop to Yard Track 3
                    // --------------------------------------------------------------
                    mast->createRoute("LOOP-YL-YT3",  Aspects::DIVERGING_APPROACH);
                    mast->addRouteDependency("LOOP-YL-YT3",  fieldUnit->get("CP_Watsonville_S:907T2"),     TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-YT3",  fieldUnit->get("CP_Watsonville_S:3SAT"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-YT3",  fieldUnit->get("CP_Watsonville_S:YLAD"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-YT3",  fieldUnit->get("CP_Watsonville_S:907"),       SwitchDevice::REVERSE);
                    mast->addRouteDependency("LOOP-YL-YT3",  fieldUnit->get("CP_Watsonville_S:909"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-YL-YT3",  fieldUnit->get("CP_Watsonville_S:902"),       SignalDevice::LEFT);
                    // --------------------------------------------------------------
                    // Route "LOOP-YL-YT4" Reverse Loop to Yard Track 4
                    // --------------------------------------------------------------
                    mast->createRoute("LOOP-YL-YT4",  Aspects::DIVERGING_APPROACH);
                    mast->addRouteDependency("LOOP-YL-YT4",  fieldUnit->get("CP_Watsonville_S:909T2"),     TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-YT4",  fieldUnit->get("CP_Watsonville_S:4SAT"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-YT4",  fieldUnit->get("CP_Watsonville_S:YLAD"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-YL-YT4",  fieldUnit->get("CP_Watsonville_S:909"),       SwitchDevice::REVERSE);
                    mast->addRouteDependency("LOOP-YL-YT4",  fieldUnit->get("CP_Watsonville_S:902"),       SignalDevice::LEFT);
                // --------------------------------------------------------------
                // CP_Watsonville_S:902SA Dwarf: Leaving Yard Track 1 Southbound into Reverse Loop
                // --------------------------------------------------------------
                //
                mast = new SignalHead_1HeadColorLight("CP_Watsonville_S:902SA", CP_Watsonville_S_902SA1F, CP_Watsonville_S_902SA2F );
                s->addHead(mast);
                    // --------------------------------------------------------------
                    // Route "Y1-LOOP" Y1 to LOOP
                    // --------------------------------------------------------------
                    mast->createRoute("Y1-LOOP",      Aspects::APPROACH);
                    mast->addRouteDependency("Y1-LOOP",      fieldUnit->get("CP_Watsonville_S:LOOP"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("Y1-LOOP",      fieldUnit->get("CP_Watsonville_S:YLAD"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("Y1-LOOP",      fieldUnit->get("CP_Watsonville_S:903"),       SwitchDevice::REVERSE);
                    mast->addRouteDependency("Y1-LOOP",      fieldUnit->get("CP_Watsonville_S:905"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("Y1-LOOP",      fieldUnit->get("CP_Watsonville_S:907"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("Y1-LOOP",      fieldUnit->get("CP_Watsonville_S:909"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("Y1-LOOP",      fieldUnit->get("CP_Watsonville_S:902"),       SignalDevice::RIGHT );
                // --------------------------------------------------------------
                // CP_Watsonville_S:902SB Dwarf: Leaving Yard Track 2 Southbound into Reverse Loop
                // --------------------------------------------------------------
                //
                mast = new SignalHead_1HeadColorLight("CP_Watsonville_S:902SB", CP_Watsonville_S_902SB1F, CP_Watsonville_S_902SB2F );
                s->addHead(mast);
                    // --------------------------------------------------------------
                    // Route "Y2-LOOP" Y2 to LOOP
                    // --------------------------------------------------------------
                    mast->createRoute("Y2-LOOP",      Aspects::APPROACH);
                    mast->addRouteDependency("Y2-LOOP",      fieldUnit->get("CP_Watsonville_S:LOOP"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("Y2-LOOP",      fieldUnit->get("CP_Watsonville_S:YLAD"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("Y2-LOOP",      fieldUnit->get("CP_Watsonville_S:905"),       SwitchDevice::REVERSE);
                    mast->addRouteDependency("Y2-LOOP",      fieldUnit->get("CP_Watsonville_S:907"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("Y2-LOOP",      fieldUnit->get("CP_Watsonville_S:909"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("Y2-LOOP",      fieldUnit->get("CP_Watsonville_S:902"),       SignalDevice::RIGHT );
                // --------------------------------------------------------------
                // CP_Watsonville_S:902SC Dwarf: Leaving Yard Track 3 Southbound into Reverse Loop
                // --------------------------------------------------------------
                //
                mast = new SignalHead_1HeadColorLight("CP_Watsonville_S:902SC", CP_Watsonville_S_902SC1F, CP_Watsonville_S_902SC2F );
                s->addHead(mast);
                    // --------------------------------------------------------------
                    // Route "Y3-LOOP" Y3 to LOOP
                    // --------------------------------------------------------------
                    mast->createRoute("Y3-LOOP",      Aspects::APPROACH);
                    mast->addRouteDependency("Y3-LOOP",      fieldUnit->get("CP_Watsonville_S:LOOP"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("Y3-LOOP",      fieldUnit->get("CP_Watsonville_S:YLAD"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("Y3-LOOP",      fieldUnit->get("CP_Watsonville_S:907"),       SwitchDevice::REVERSE);
                    mast->addRouteDependency("Y3-LOOP",      fieldUnit->get("CP_Watsonville_S:909"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("Y3-LOOP",      fieldUnit->get("CP_Watsonville_S:902"),       SignalDevice::RIGHT );
                // --------------------------------------------------------------
                // CP_Watsonville_S:902SD Dwarf: Leaving Yard Track 4 Southbound into Reverse Loop
                // --------------------------------------------------------------
                //
                mast = new SignalHead_1HeadColorLight("CP_Watsonville_S:902SD", CP_Watsonville_S_902SD1F, CP_Watsonville_S_902SD2F );
                s->addHead(mast);
                    // --------------------------------------------------------------
                    // Route "Y4-LOOP" Y4 to LOOP
                    // --------------------------------------------------------------
                    mast->createRoute("Y4-LOOP",      Aspects::APPROACH);
                    mast->addRouteDependency("Y4-LOOP",      fieldUnit->get("CP_Watsonville_S:LOOP"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("Y4-LOOP",      fieldUnit->get("CP_Watsonville_S:YLAD"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("Y4-LOOP",      fieldUnit->get("CP_Watsonville_S:909"),       SwitchDevice::REVERSE);
                    mast->addRouteDependency("Y4-LOOP",      fieldUnit->get("CP_Watsonville_S:902"),       SignalDevice::RIGHT );
            // ===================================================================
            // CP_Watsonville_S Signal 904: Departure Track to/from Reverse Loop
            // ===================================================================
            s = (SignalDevice *)fieldUnit->get("CP_Watsonville_S:904");
                // --------------------------------------------------------------
                // CP_Watsonville_S:904NA Reverse Loop to Departure Track
                // --------------------------------------------------------------
                //
                mast = new SignalHead_1HeadColorLight("CP_Watsonville_S:904NA", CP_Watsonville_S_904NA1F, CP_Watsonville_S_904NA2F );
                s->addHead(mast);
                    // --------------------------------------------------------------
                    // Route "LOOP-DT" Reverse Loop to Departure Track (usual route)
                    // --------------------------------------------------------------
                    mast->createRoute("LOOP-DT",      Aspects::CLEAR);
                    mast->addRouteDependency("LOOP-DT",      fieldUnit->get("CP_Watsonville_S:901T1"),     TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-DT",      fieldUnit->get("CP_Watsonville_S:DAT"),       TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("LOOP-DT",      fieldUnit->get("CP_Watsonville_S:901"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("LOOP-DT",      fieldUnit->get("CP_Watsonville_S:904"),       SignalDevice::LEFT);
                // --------------------------------------------------------------
                // CP_Watsonville_S:904SAB Southbound on Departure Track (reverse running) to LOOP or YLAD
                // --------------------------------------------------------------
                //
                mast = new SignalHead_2HeadColorLight("CP_Watsonville_S:904SAB", CP_Watsonville_S_904SAB1F, CP_Watsonville_S_904SAB2F, CP_Watsonville_S_904SAB3F, CP_Watsonville_S_904SAB4F );
                s->addHead(mast);
                    // --------------------------------------------------------------
                    // Route "RDT-LOOP" Southbound (reverse running) direct to Reverse Loop
                    // --------------------------------------------------------------
                    mast->createRoute("RDT-LOOP",     Aspects::RESTRICTING);
                    mast->addRouteDependency("RDT-LOOP",     fieldUnit->get("CP_Watsonville_S:901T1"),     TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("RDT-LOOP",     fieldUnit->get("CP_Watsonville_S:LOOP"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("RDT-LOOP",     fieldUnit->get("CP_Watsonville_S:901"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("RDT-LOOP",     fieldUnit->get("CP_Watsonville_S:904"),       SignalDevice::RIGHT );
                    // --------------------------------------------------------------
                    // Route "RDT-Y-LOOP" Southbound (reverse running) to Reverse Loop via Yard Ladder
                    // --------------------------------------------------------------
                    mast->createRoute("RDT-Y-LOOP",   Aspects::DIVERGING_RESTRICTING);
                    mast->addRouteDependency("RDT-Y-LOOP",   fieldUnit->get("CP_Watsonville_S:901T1"),     TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("RDT-Y-LOOP",   fieldUnit->get("CP_Watsonville_S:LOOP"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("RDT-Y-LOOP",   fieldUnit->get("CP_Watsonville_S:YLAD"),      TrackCircuitDevice::UNOCCUPIED);
                    mast->addRouteDependency("RDT-Y-LOOP",   fieldUnit->get("CP_Watsonville_S:901"),       SwitchDevice::REVERSE);
                    mast->addRouteDependency("RDT-Y-LOOP",   fieldUnit->get("CP_Watsonville_S:903"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("RDT-Y-LOOP",   fieldUnit->get("CP_Watsonville_S:905"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("RDT-Y-LOOP",   fieldUnit->get("CP_Watsonville_S:907"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("RDT-Y-LOOP",   fieldUnit->get("CP_Watsonville_S:909"),       SwitchDevice::NORMAL);
                    mast->addRouteDependency("RDT-Y-LOOP",   fieldUnit->get("CP_Watsonville_S:902"),       SignalDevice::RIGHT );
                    mast->addRouteDependency("RDT-Y-LOOP",   fieldUnit->get("CP_Watsonville_S:904"),       SignalDevice::RIGHT );
    Serial.print("Heap: ");
    Serial.print((startmem - finishmem) / 1024);
    Serial.print("k used out of ");
    Serial.print(startmem / 1024);
    Serial.print("k total (");
    Serial.print((startmem - finishmem) / startmem);
    Serial.print("%) leaving ");
    Serial.print(finishmem / 1024);
    Serial.print("k free");
    Serial.println();
}

void loop(void) {
    bool somethingchanged = false;
    if (otaTime > DELAY_OTA) {                              // Check connection to WiFi/MQTT/OTA Firmware updates
        somethingchanged = codeline->CheckCodeLine();
        otaTime = 0;
    }
    if (displayTime > DELAY_DISPLAY) {                      // Update the display
        displayTime = 0;
        codeline->update(MaintainerDisplay::REFRESH);
    }
    if (somethingchanged || (checkTime > DELAY_CHECK)) {    // check the field appliances and process changes
        fieldUnit->run(somethingchanged);
        checkTime = 0;
    }
}

 
~~~
