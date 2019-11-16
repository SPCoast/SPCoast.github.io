---
project: project_design
title: Before you begin
---

As they say, the best way to finish something is to start; there are
several things you can do to your EagleCad environment to have it start
with comfortable settings every time. I\'ve combined my preferred
initialization and several \"macros\" for Eagle into a couple reusable
EagleCAD scripts that you can download and use. Simply save them in a
directory that can be found in EagleCAD\'s SCRIPT path (control
panel-\>Options-\>Directories-\>Scripts) and invoke it in the board or
schematic editor window like this:

:   `script /path/to/SPCoast.scr`

Once you have done this, the settings will be autosaved in your .eaglerc
startup file and you won\'t need to rerun these SCRipts again unless you
want to change things.

See below for a description of these commands.

Getting EagleCAD:

-   [CadSOFT web site](http://www.cadsoftusa.com/download-eagle/)
    Official site, includes free hobby version
-   [AdaFruit](https://www.adafruit.com/products/1615) US distributer,
    great for non-hobby users

Scripts:
\[<http://>`{{SERVERNAME}}`{=mediawiki}/pub/download/scripts/Scripts-SPCoast.scr-SPCoast.scr
SPCoast.scr\],
\[<http://>`{{SERVERNAME}}`{=mediawiki}/pub/download/docs/Documents-PCB-Design-howto-colors.scr
colors.scr\] and
\[<http://>`{{SERVERNAME}}`{=mediawiki}/pub/download/docs/Documents-PCB-Design-howto-layers.scr
layers.scr\]

Dropbox
-------

I have several computers where I run EagleCAD - laptops, desktops, at
home, at [TechShop](http://www.techshop.ws/ts_sanjose.html), at work and
on the road. The terms of my Eagle license allow this - as long as my
alternate personalities aren\'t using more than one at the same time.

To solve the problem of keeping everything in sync, I created a
directory named \"eagle\" in my Dropbox folder so that, no matter what
computer I\'m using, I have access to the latest revisions. Eagle lets
me define a set of project directories in the main Eagle Control Panel
window\'s \[Options-\>Directories\] menu.

Of course, Google Drive, Microsoft OneDrive, Box.com and others can be
used instead of Dropbox\...

1.  Create a -project dir- for your EagleCAD projects in your Dropbox
    folder (I call mine \"eagle\")

    :   \~/Dropbox/eagle/
    :   

2.  Create subdirs in it for libraries, scripts and CAM files. I chose
    to put all the eagle specific stuff under a common Library
    subdirectory:

    :   \~/Dropbox/eagle/

        :   Libraries/

            :   scr
            :   cam
            :   ulp
            :   dru

3.  in EagleCADs console window edit the Options-\>Directories content
    to match (The entries there are \":\" separated lists of
    directories)

:   ![](Documents-PCB-Design-howto-EagleCAD-Directory-preferences.png "fig:Documents-PCB-Design-howto-EagleCAD-Directory-preferences.png"){width="500"}\
    EagleCAD Directory Options

You can see that I have both projects and shared library stuff (dru
files, cam jobs, ulp scripts\...) in my dropbox hierarchy.

Version Control
---------------

Eagle feels stuck in the dark ages when it comes to version control. It
presumes a strict 1:1 relationship between a schematic and a board
design, and it has no provision for managing versions. Yes, it does
create a sequence of .b\#1 and .s\#2 editing backups as you change
things, and yes, it has a robust ULP and SCRipting system, but it leaves
everything up to you to handle manually.

There are a couple of attempts out there to add GIT support to Eagle
([jotux eagle-diff](https://github.com/jotux/eagle-diff), [lcox
esawdust](http://www.esawdust.com/blog/EaglePCB/EaglePCB_files/gitforembedded.html),\...),
but none really deal with the subtle distinction between backups (for
safety as you develop) and archives (for safety after you are done with
a version). What follows is the workflow and practices I\'ve developed
to address those needs.

### Names?

It may seem obvious, but names matter, as does consistency. I\'ve
chosen to create project directories that are named the same as the
project they contain, without any version numbers or added descriptive
annotations. In the project directory, I then create a set of
**versioned subdirectories** that hold the various versions and
derivations I create for that project, and in those subdirectories, I
place the schematic and board files.

My naming scheme is based on major.minor indications, that work in
progress is in just another subdirectory, and that the difference
between a major and minor version is whether or not the schematic has
changed significantly.

In the PC world where I started off,
[ExpressPCB](http://www.expresspcb.com/) has a CAD package that links
PCBs back to a schematic, but the schematic doesn\'t know about the
boards that are derived from it. This lets me have several different
PCB designs based on a single schematic. This fit my workflow of
creating a logical design (schematic) and then iterating on various
board designs until I decide to fab a sample board.

While EagleCAD doesn\'t do this the same way, I have found a way to
get the same result - a set of versioned project directories with the
.sch and .brd files the way they were for that version:

-   I open the project I want to clone/change (i.e.,
    \.../Detector/1.0/Detector.sch),
-   Immediately do a \"Save As\", which pops up a dialog
-   create a new subdirectory (i.e., \.../Detector/1.1), and finally
-   save the project there,

When compared to the PC software, this leaves me with extra copies of
the same schematic in each subdirectory, but gives me the unique board
files.

:   \~/Dropbox/eagle/
:       Detector/
:           1.0/
:               Detector.sch
:               Detector.brd
:           1.1/
:               Detector.sch
:               Detector.brd
:           2.0/
:               Detector.sch
:               Detector.brd

### Project Backups 

My eagle working directory is a Dropbox folder, and Dropbox supports
file versioning and overwrite protections Because of this, I never
worry about safety copies of my files unless I\'m working on my laptop
somewhere with no network access.

### Project Archives 

Archives, on the other hand, are copies of my project at milestone
points in the development life of the project. Maybe I just want to
share a design with others for comments, or maybe I want to fab a
sample board - or (rarely :smile: ) I\'m actually done and ready to
fab a larger production batch - at these points in time, it is
important to be able to reference the sch/pcb files exactly as they
were.

#### First Attempt 

My first workflow based archiving effort leveraged the built in CAM
processor and a shell script. Whenever I was ready to share, I ran
the EagleCAD CAM processor with a custom [ JMP-gerber CAM
Job](JMP-gerber "wikilink"), then ran my
[Makeboard](Makeboard "wikilink") script to create an archive
subdirectory, copy the schematic, board and CAM job output files
into it, and generate tar and zip files for submission to fabs; the
script also copied the resulting gerber zip file to a
\"CurrentOrders\" directory to remind me what I need to order next
time I did a fab run:

``` {.html4strict}
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04/IO4-ArdIOShield.brd
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04/IO4-ArdIOShield.eagle.tar
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04/IO4-ArdIOShield.GBL
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04/IO4-ArdIOShield.GBO
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04/IO4-ArdIOShield.GBS
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04/IO4-ArdIOShield.gerbers.tar.gz
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04/IO4-ArdIOShield.gerbers.zip
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04/IO4-ArdIOShield.GTL
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04/IO4-ArdIOShield.GTO
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04/IO4-ArdIOShield.GTP
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04/IO4-ArdIOShield.GTS
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04/IO4-ArdIOShield.sch
IO4-ArdIOShield/2.0-ProMini-Grey3/Archive/Gerbers.IO4-ArdIOShield.2014-12-31-21:36:04/IO4-ArdIOShield.TXT
```

#### Second attempt 

I quickly got tired of \"click CAM, click Load job, click run job,
then go to another window and run the shell script\". I also found I
wanted pictures of the schematic and board that I could post on this
website (which entailed more click-and-type-and-click followed by
more scripting\...). With a bit of googleing and (gasp!) reading the
manual, I was able to figure out how to invoke scripts and programs
from within EagleCAD. Along the way, I convinced myself that this
was too hard, and decided there should be a better way: I could do
it the other way around and run a script that invoked EagleCAD. This
path had/has its own share of issues - including CadSoft\'s
inability to keep releases backwards compatible, but with a little
bit of fiddling once a year or so, it works!

The script I wrote:

-   invokes EagleCAD to generate the CAM job files
-   invokes it again to generate the various images
-   runs [Makeboard](Makeboard "wikilink") on the artifacts, and
    even
-   uploads the results to this website.

I started documenting my projects by adding a DESCRIPTION file to
each project directory. EagleCad uses the first line in its control
panel to tell you a bit more about the project, and ignores the
rest. I took advantage of this and added wiki markup text to the
end. Soon, I was adding jpg photos of boards, PDF files and other
artifacts, and the script got more and more complex; I refactored it
several times now, and it is pretty stable.

The workhorse scripts to look at are
[Makeboard](Makeboard "wikilink"), [DoEagle](DoEagle "wikilink") and
[Upload2web](Upload2web "wikilink").

I typically run\
`doEagle _project_` in the versioned subdir of a project I\'m
working on to archive and CAM things, followed by\
`cd ..;upload2web _project_` to update the website.

I wrapped them in a set of Makefiles and am able to easily
regenerate all the eagle project info in this wiki with a single
command.

Make a symlink to this Makefile in each eagle project subdirectory (
ln -s ../Makefile.project Makefile )

``` {.make .numberLines}
SUBDIRS := $(wildcard */.)
SUBDIRS := $(subst /.,/,$(SUBDIRS))
PROJECT := $(shell basename $$PWD)


all:  upload

upload: $(SUBDIRS)
        upload2web

subdirs: $(SUBDIRS)

.PHONY: subdirs $(SUBDIRS)

$(SUBDIRS):
        @echo "==== $@ ===="
        @(\
                if [ ! -f $@/Makefile  -a ! -h $@/Makefile ]; then (cd $@; set -x; ln -s ../../Makefile.board Makefile); fi; \
        )
        @PROJECT="$(PROJECT)" $(MAKE) -C $@
```

Makefile.board - in the each individual project version directories.

``` {.make .numberLines}
all: gerbers
clean:

gerbers:
        @\
        if [ -z "$(PROJECT)" ]; then \
                parent=`cd ..; pwd`; \
                PROJECT=`basename $$parent`; \
        fi; \
        (set -x; doEagle $$PROJECT); 
```

MacOS/Linux shell scripts:

-   [upload2web](upload2web "wikilink") - a shell script to do CAM
    processing, archiving and wiki website content updating.
    Presumes doEagle has been run.
-   [DoEagle](DoEagle "wikilink") - a shell script that does the CAM
    job processing (and more) by invoking EagleCAD from the command
    line.
-   [WalkSite](WalkSite "wikilink") - a shell script to walk thru a
    project directory tree and validate/fix the file and
    subdirectory naming schemes
-   [mvname](mvname "wikilink") - a shell script that renames files
    in bulk (change foo.\* to barbaz.\*)

Schematic Layout 
----------------

Here\'s where the basic hygiene comes in. There are a few simple, but
often unstated, rules that will make things much easier for you when you
interact with the larger Eagle community:

-   Use a **0.100\" (100 mil) grid** for your schematic layout.
    Gratuitously violating this rule (especially when creating reusable
    library parts - I\'m looking at you, seeed OPL\...) will let you
    create parts that WILL NOT CONNECT to each other. If you mess up,
    the standard EagleCad ULP \"\"snap-on-grid-sch.ulp\"\" can help
    -   GRID = SCH mil 100 1 dots on alt mil 50;
-   It can be a pain, but it really helps when it comes time to buy the
    parts for your project if you assigned correct values to all the
    parts
    -   Since the silk screen for a decimal point is often impossible to
        see, I use a labeling scheme where the decade multiplier acts a
        decimal point: 2m, 2m2, 220k, 22k, 2k2, 220R for 2meg, 2.2meg,
        220k, 22k, 2.2k and 220 ohms.
    -   I\'m a bit lazy here - standard things like breakaway 100mil pin
        headers and standard connectors don\'t always get a value
-   Use a FRAME-LETTER part on each schematic sheet that records the
    metadata about that design. Place the Frame origin at (0,0)
-   Use named nets, XREF symbols and grouped subassemblies to keep your
    schematic neat and organized
    -   Use the GND symbol for ground connections instead of running a
        continuous wire net everywhere on the schematic. (If you use a
        square pad for grounds on your PCB, it makes it easier to
        trace/test a board, too!)
    -   Use the same VCC symbol for all connections that require that
        power source (VCC, 5V, 3.3V, VIO,\...)
-   I like to use grey dashed lines (layer 97, Info) to separate complex
    subassemblies into smaller bits (power supply, IO drivers\...)

PCB Layout 
----------

-   Use a 0.100\" (100 mil) grid for your PCB dimensions, with one
    corner at (0,0).
    -   GRID = BRD mil 50 2 dots on alt mil 25;
    -   GRID = FINE mil 50 2 dots on alt mil 1;
-   For [Seeed
    Fusion](http://support.seeedstudio.com/knowledgebase/articles/422482-fusion-pcb-order-submission-guidelines)
    boards (which are priced based on 5cm increments), make it easy on
    yourself when setting board dimensions: use a 10mm grid with a 5x
    visible multiplier, set your board dimensions, then change back to
    the standard 50mil grid.
    -   GRID = DIM mm 10 5 lines on alt mm 1;

:   

    :   ![](Documents-PCB-Design-howto-EagleCAD-Grid.png "fig:Documents-PCB-Design-howto-EagleCAD-Grid.png"){width="300"}

\
\* Consider amenities like rounded corners and STANDOFFS

-   -   Standoffs (aka mounting holes) make it easy to mount your board
        to a case or backboard
    -   Rectangular boards are easiest to fabricate and handle, but feel
        free to make the board outline fit your enclosure.

:   

    :   I prefer 50-mil radius rounded corners and a 0-width dimension
        line

<!-- -->

:   

    :   ![](Documents-PCB-Design-howto-50-mil-radius-dimension.png "fig:Documents-PCB-Design-howto-50-mil-radius-dimension.png"){width="300"}

-   Place parts on a 0.05\" (50 mil) grid. The standard EagleCad ULP
    *cmd-snap-board.ulp* can help fix an existing board.
-   Use 10mil or 12mil traces as a default, with 8mil as an absolute
    minimum, as fab problems are more likely with small traces and
    inexpensive board houses\.... Power traces should be 12mil or 16mil
    (500mA), with 24mil for \>1A. For model railroad applications, DCC
    Track currents may reach 8A or more, with 200-500mil required trace
    widths!
-   Keep at least 8mil between traces, 12mil between power routes.
-   Manual routing always produces a better board - only use the
    autorouter for prototypes!
-   Manual routing always produces a better board - only use the
    autorouter for prototypes! No, this isn\'t a typo!
    -   Route with straight traces and 45 degree corners. Avoid 90
        degree corners, especially on hi frequency signal runs or thin
        traces.
    -   Route from the center of every pad, not from the edges
    -   Avoid concave trace/pad connections which can allow etchant to
        eat into the pad/trace.
    -   If something will be soldered into a hole, use a via with a
        larger annular ring (See DRC \"Restring\" page) so that it is
        easier to solder
        -   A good default: 0.04\" (40mil) hole with 0.074\" (74mil)
            diameter (not auto)
-   Use ground pours on both the top and bottom layers.
-   If you use fill polygons, make sure you set an *isolate* value of at
    least 8mil to 10mil!
-   Set the default via size to 0.020 (20mil)
    -   The smallest via you should use is 0.015 (15mil) (defined by the
        Drill parameter), smaller invites drilling errors by the board
        house
-   Any panelized assemblies should have at least 3 (three) FIDUCIALS
    -   Placing Fiducials on a board makes it easier to orient stencils
        and align automated test/assembly fixtures
    -   Fiducials (FIDs) are a set of (usually) 3 non-symetrical holes
        placed around the periphery of a panel of boards such that
        -   if there were mounting pins for each fiducial, there would
            be only one correct way to mount the board
            (left/right/top/bottom\...)
        -   the distance between the holes is as large as practical, and
        -   the distances between each hole are similar
        -   pick and place machines use these FIDs to correctly find and
            place components on your boards, even if the board is
            slightly misaligned

![](Documents-PCB-Design-howto-EagleCAD-Color-palette-default-black.png "fig:Documents-PCB-Design-howto-EagleCAD-Color-palette-default-black.png"){width="200"}
![](Documents-PCB-Design-howto-EagleCAD-Color-palette-default-white.png "fig:Documents-PCB-Design-howto-EagleCAD-Color-palette-default-white.png"){width="200"}![](Documents-PCB-Design-howto-EagleCAD-Color-palette-custom-black.png "fig:Documents-PCB-Design-howto-EagleCAD-Color-palette-custom-black.png"){width="300"}
![](Documents-PCB-Design-howto-EagleCAD-Color-layers.png "fig:Documents-PCB-Design-howto-EagleCAD-Color-layers.png")

-   EagleCAD\'s default color schemes are OK, but could be improved. If
    you do change the colors, be sure to keep the Alpha value (the first
    2 hex digits in the color setting in the defaultcolors.scr script)
    the same (180 or 200 decimal, 0xB4 or 0xC8 in hex) so that the
    automatic highlighting in Eagle works. The palette entries are
    grouped into \"normal\" and \"highlight\" colors. There are always 8
    \"normal\" colors, followed by the corresponding 8 \"highlight\"
    colors. So colors 0..7 are \"normal\" colors, 8..15 are their
    \"highlight\" values, 16..23 are another 8 \"normal\" colors with
    24..31 being their \"highlight\" values and so on. The \"highlight\"
    colors are used to visualize objects, for instance in the SHOW
    command. The alpha component defines how \"opaque\" the color is. A
    value of 0x00 means it is completely transparent (i.e. invisible),
    while 0xFF means it is totally opaque. The alpha component of the
    background color is always 0xFF.
-   Note that the palette entry number 0 is used as the background color
    (in the \"white\" palette this entry cannot be modified, since this
    palette will also be used for printing, where the assumption is that
    the paper (the printer\'s background color) is always white).
-   If you want to change the colors used when printing your schematic
    and board, change the \"White\" palette. Remember, the \"colors\"
    used in the LAYERs dialog are really offsets into the color table
    (so Top=RED below is really Top=(the color in cell 4, which happens
    to be RED)
-   I use the following colors:
    -   Layer 1, Top - Red
    -   Layer 16, Bottom - Green
    -   Layer 17, Pads - golden brown
    -   Layer 18, Vias - golden brown
    -   Layer 19, Unrouted - bright orange
    -   Layer 20, Dimension - slate
    -   Layer 21, tPlace - dark blue
    -   Layer 22, bPlace - loghter blue
    -   Layer 48, Document - Yellow
    -   Layer 49, Reference - Orange
    -   Layer 51, tDocu - light yellow
    -   Layer 52, bDocu - grey

![](Eagle-IO4-ArdIOShield-2.0-ProMini-Grey3-IO4-ArdIOShield.brd.png "Eagle-IO4-ArdIOShield-2.0-ProMini-Grey3-IO4-ArdIOShield.brd.png"){width="300"}

-   I define several layer aliases that make it easy to focus on
    different parts of your pcb (see
    [SPCoast.scr](SPCoast.scr "wikilink"))
    -   (You could copy/paste these command lines into the text box at
        the top of your eagle board editor, and then access the
        resulting menu with a Right-Click on the Layers/DISPLAY icon):

`Display = Normal    NONE 1 16 17 18 19 20 21    23    25    27    39      41 42 43 44 45 46 47 48 49 51    101 102 104;`\
`Display = Reverse   NONE   16 17 18 19 20    22    24    26    28     40     42    44 45 46 47          52;`\
`Display = TopSilk    NONE      17 18    20 21                                                         51;`\
`Display = BotSilk    NONE      17 18    20    22                                                         52;`\
`Display = Unrouted  NONE      17    19 20;`

-   If you grouped parts together on the schematic, try to place them
    near to each other on the PCB.
-   Use the design rules check tool along with a DRU file from your
    board house
    -   SparkFun: [DRU file - 2
        layer](https://github.com/sparkfun/SparkFun_Eagle_Settings/blob/master/dru/SparkFun-2-layer.dru)
    -   SparkFun: [DRU file - 4
        layer](https://github.com/sparkfun/SparkFun_Eagle_Settings/blob/master/dru/SparkFun-4-layer.dru)
    -   Seeed Fusion: [DRU file - 2
        layer](http://www.seeedstudio.com/document/rar/SeeedStudio_DRU_no_angle_20130527.zip)

Silkscreen
----------

-   Place the project name and version on the board (Detector v1.3
    2013.12)
-   Add a date code somewhere on the board (bottom is OK)
-   Branding is important: SPCoast boards always have a Railroad Track
    logo somewhere on the back silkscreen, along with a website
    reference, a NMRA/Pacific Coast Region plug and the phrase \"Model
    Railroading is fun!\":

![](Eagle-IO4-ArdIOShield-2.0-ProMini-Grey3-IO4-ArdIOShield.bot.brd.png "Eagle-IO4-ArdIOShield-2.0-ProMini-Grey3-IO4-ArdIOShield.bot.brd.png"){width="300"}

-   Label text sizes smaller than 40mil are effectively illegible.
    Consider 32mil to be the absolute minimum, with 50mil a good
    default.
-   All LEDs, connectors, switches, jumpers and jacks must be labeled
    with their purpose: Power, Reset, On/Off, IO Port A; not LED3,
    Switch or RJ45\...
-   Unpolarized Connectors and headers must have pin1 marked by a dot or
    the numeral 1.
-   Pay attention to text alignment - aesthetics matter!
