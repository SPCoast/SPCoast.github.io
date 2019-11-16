---
title: Project Assembly Notes
sidebar: spcoast_sidebar
keywords: soldering, safety
permalink: project_assembly.html
toc: false
folder: pages
---

Identify the parts {#identify_the_parts}
------------------

First off, you need to identify all the parts and understand their
markings: Resistors are marked with multi-colored bands that signify
their resistance in ohms. Diodes have a black band at one end,
electrolytic capacitors have their polarity marked with a "-" next to
their short lead, integrated circuits have a dot or a notch on the end
with pin 1, etc.

All statements relating to orientation are with the top of the board up
(you should see the "component" label on the board. If you see the word
"solder" instead, look at the other side).

Order of assembly {#order_of_assembly}
-----------------

Assembly order is not really important, except for components that are
tightly packed together - in general, insert the smaller ones first,
proceed to the larger objects (sockets...) and finish off with
connectors and heatsinks.

Check off each item as it is completed. Insert the part, solder it in
then inspect the solder joint to make sure it shines (a dull color
indicates a cold joint, which is not good - simply reheating it and
letting it cool without moving the part will usually fix a cold joint).
Once a part is correctly soldered in place, cut off the excess length
leads on the bottom of the circuit board.

Safety First {#safety_first}
------------

Heat is the most obvious danger. Solder starts to melt at around 250 C
but the iron tip needs to be hotter than this to ensure a good flow of
solder. Special holsters or rests with safety guards are available for
soldering irons and these should be used.

Keep small children out of the room while the soldering iron is hot.
Don\'t wear your best clothes because you may burn the material or
splash molten solder on it. If you don\'t wear glasses then eye
protection is strongly recommended.

If you do burn yourself, get the affected body part immediately under
cold, running water. Plunging it into a jug of cold water is the next
best thing but, whatever you do, keep the skin wet for at least ten
minutes. Flesh carries on \"cooking\" for a long time after the initial
injury has occurred. Seek medical advice if the burn is more than 5mm
wide or if you suffer from an ailment such as diabetes or if you are in
any doubt about the ability of your skin to heal. Burns can become
infected. (Some people I know keep an aloe plant near their workbench so
that they can apply fresh \"aloe vera ointment\" to their burns - for
myself, I really like to not get burned in the first place)

Solder is a mixture of lead and tin. Lead is is bad for everyone, but it
is especially dangerous to growing children. It\'s a bad idea to put
solder in your mouth or use it to stir your tea! Wash your hands after
using it and don\'t bite your nails. Molten solder (actually, boiling
Lead) could emit atoms of lead into the air but, in practice, the solder
doesn\'t reach that high of a temperature. Nevertheless you should use
the soldering iron in a well-ventilated room. I know several people who
have recycled a PC case fan to keep fumes out of their face\...

Sharp edges can give you a nasty cut. The snipped component wires
beneath the circuit board are like thorns and they fly off in all
directions when cut. Sharp IC pins seem to be attracted to fingers, and
you always can find the one that fell on the floor by walking into the
room in bare feet!

You are dangerous to ICs and semiconductors! If you wear synthetic fiber
clothing (nylon, rayon\...), walk across a nylon carpet or do anything
to acquire a charge of static electricity, you can discharge several
thousand volts into a circuit when you touch it. Integrated Circuits are
static sensitive devices. Don't remove them from their anti-static
storage packages until you are ready to install them and then don't
touch their pins. It is best not to work in a carpeted room. Always make
sure you discharge yourself (by touching some grounded metal) before you
handle semiconductors or circuit boards.

Soldering tips {#soldering_tips}
--------------

Soldering is rather easy as long as you have the correct tools and are
neat. You should use a small soldering iron, 15 to 25 watts. Also use
the thinnest solder that you can find. Make sure you are using solder
for electrical parts and **DO NOT use acid core solder** under any
circumstances.

### Soldering basics {#soldering_basics}

-   Keep the soldering iron tip clean with a damp sponge and tin it with
    fresh solder before use. Wipe off excess solder on the sponge.
    Don\'t use the iron to carry solder to the joint.
-   Bend the component wires to match the distance between the holes.
    The resistors and diodes will fit well with a 0.4\" lead spacing -
    which is easy to apply with a lead bending tool. Fit the component
    from the top side of the board (make sure that it is oriented the
    right way) by pushing it down gently until it reaches the board.
-   Once the component is seated, slightly bend the leads beneath the
    board in the direction of the connecting PCB trace (if possible). A
    45 degree bend is adequate to keep the part from falling out when
    you turn the board over to solder it. Solder the joints by pressing
    the iron tip against the wire and the copper pad and applying solder
    to both. Rotate the iron tip back and forth to assist heat
    conduction, cleaning and solder flow.
-   Once solder has melted, flowed into and filled the joint, remove the
    soldering iron without disturbing the joint and let the molten
    solder solidify.
-   Inspect the solder joint to make sure it shines (a dull color
    indicates a cold joint, which is not good - simply reheating it and
    letting it cool without moving the part will usually fix it)
-   Surface mount soldering is easier to do than it is to explain,
    especially if you have mastered the through-hole style. There are
    many good writeups on the \'net and on youtube. Google( Surface
    Mount Soldering ) to find sites like this [SMD Soldering
    Guide](http://www.infidigm.net/articles/solder/) and the [Curious
    Inventor](http://store.curiousinventor.com/guides/) site.
    [Sparkfun](http://www.sparkfun.com) is also a great resource\...
