---
title: Brakeman
project: Brakeman
datasheets:
- name: LED-Red-XingLight-XL-1608SURC-06
  view: https://github.com/plocher/SPCoast-inventory/blob/main/datasheets/LED-Red-XingLight-XL-1608SURC-06.pdf
  download: https://raw.githubusercontent.com/plocher/SPCoast-inventory/main/datasheets/LED-Red-XingLight-XL-1608SURC-06.pdf
- name: Resistor-ThickFilm-Uniroyal-series
  view: https://github.com/plocher/SPCoast-inventory/blob/main/datasheets/Resistor-ThickFilm-Uniroyal-series.pdf
  download: https://raw.githubusercontent.com/plocher/SPCoast-inventory/main/datasheets/Resistor-ThickFilm-Uniroyal-series.pdf
---
## Brakeman

## License: CERN Open Hardware Licence v1.2

An electronic DCC-track-driven figurine with a red or blue LED

## GCOR Rule 6.19 D (paraphrased)
> When a train stops on a main track, flag protection must be provided
> On a layout, torpedoes and fusees are a bit over the top, but a
> brakeman/flagman with a red lantern can add a twist to your next operating
> session.  Adopt prototype practices and have your crews protect
> their trains when switching a town or otherwise fouling the main.
> Just don't forget to recall the flagman before leaving town!


## Designed in the NMRA/PCR for DCC layouts

The HO DCC Flag man, gives the Time Table and Train Order (TT&TO) operator a convenient way to "flag out" and warn other trains that he's occupying main track, it also serves as handy DCC track power tester!  The Flag man has contacts that bridge the track (and trigger occupancy circuits) and light a 2 LED "lanterns" to warn approaching trains of his presence.  

The project supports two variants - default (red) for a flagman, and Blue for Safety Sam marking a piece of rolling stock or track out of service
 
Assembly required
1. V1.0-1.3: Use a track nipper to detach the base from the hand holding the LED.
1. V1.4: Snap the base from the feet and remove any extra PCB frame from around the figure.
1. Solder the two feet to the two small gold pads on the top of the base
1. You can solder a wire (the clipped off resistor leads work well) to strengthen and align this connection
1. Attach the weight to the top of the base next to (but not touching) his feet with double sided foam tape
1. Place the large gold pads across the rails to light the red lantern.

Variation:
  * Make a "Safety Sam" to indicate track or rolling stock that must not be used/moved.  Use 2 BLUE LEDs instead of RED ones 

Clean track works best.  Use violates UP Safety Rule 81.2.1, Step Over Rail 

John Plocher, SPCoast.com

> WARNING: This product may contain chemicals known to the State of California to cause cancer and birth defects or other reproductive harm. 


  * Designed for fabrication and ease of assembly

For best results when fab'ing, choose:

  * ENIG (gold) rather than a Hot Air Solder Layer (HASL) for the pads
  * White or Blue soldermask
  * Panalize = 1
