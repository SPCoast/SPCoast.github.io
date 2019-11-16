---
title: Project Fabrication Notes
sidebar: spcoast_sidebar
keywords: fabrication, pcbs
permalink: project_fabrication.html
toc: false
folder: pages
---

I use the following workflow to upload and order boards from [Seeed
Studio](http://seeedstudio.com)\] and [BatchPCB](http://batchpcb.com)

First, set up EAGLE and customize it\'s environment and behavior to your
liking.

1.  Obtain the latest version of Cadsoft\'s Eagle program
2.  Download a .dru rules file that encodes BatchPCB\'s and/or Seed
    Fusion\'s requirements. I use [a 10-mil version of SparkFun\'s DRU
    file](http://www.spcoast.com/pub/CP/SparkFun10mil.dru)
3.  Put a copy of the file (with the .dru extension) in the Eagle
    program\'s dru directory (on my Mac, this is at
    Applications/Eagle/dru/SparkFun10mil.dru )
4.  Download a .cam processor definition file that you can use to create
    \"gerber\" and \"drill\" files for your fab house. I tweeked the
    SparkFun one to use additional layers and not generate a mill file,
    you can download
    [JMP-gerb274x.cam](http://www.spcoast.com/pub/CP/JMP-gerb274x.cam)
    and put it in Eagle\'s cam directory
    (Applications/Eagle/cam/JMP-gerb274x.cam)
5.  ON MACOS and Linux: I use a homegrown [shell
    script](http://www.spcoast.com/pub/CP/makeboard)   that will archive
    old files and collect things for a fab house submission and put it
    somewhere where you can find it easily - I put the script in my
    \$HOME/bin subdirectory and make sure my PATH references it as
    **makeboard**.
6.  Tell Eagle to use the rules file when autorouting: (Tools)-\>(DRC),
    (Load) dru/SparkFun10mil.dru

Second, pick a fab house. I\'ve used both
[BatchPCB](http://batchpcb.com/) and [Seeed Studio\'s Fusion
Service](http://www.seeedstudio.com/depot/fusion-pcb-service-p-835.html?cPath=185);
BatchPCB was agonizingly slow (1 to 2 months!) when I last used it,
Seeed takes less than a month (half that if you pay for fast shipping)
and is a fraction of the cost (10x 5cmx5cm boards for \$10us!) You might
also want to peruse this [list of fab
houses](http://www.slugsite.com/archives/1285).

Once you have set up your EAGLE environment and have looked at the
BatchPCB and/or Seeed Fusion products, you can focus on creating boards:

1.  Create a schematic and associated PCB layout using Eagle Lite (there
    are many good tutorials on the web - I\'ll bet you can\'t tell that
    I particularly like SparkFun\'s site :-) I tend to give the files
    version numbers in their name as well as in text on the board - and
    increment the version number whenever I actually fab a board, so I
    have filenames like CANBusProtoboard-1.0.sch or
    shields/IOShield/1.3/IOShield.brd

<!-- -->

1.  When you have a PCB you like (AND HAVE CHECKED by printing 1:1 and
    making sure all your components fit), use the CAM Processor to
    generate the files that the Board house needs:
    1.  (File) -\> (CAM Processor), (File) -\> (Open)
        /Applications/EAGLE/cam/JMP-gerb274x.cam
    2.  (Process job)
    3.  dismiss the CAM Processor window - it will have created a bunch
        of files in the directory your schematic and pcb files are in
2.  I then use a helper script in a terminal window, giving it the base
    name of my project, but you can manually make a tar file out of the
    gerber and drill files and compress it with gzip if you like:
    -   plocher\@mymac\> **makeboard CANBusProtoboard-1.0**\
        This will create a subdirectory with a bunch of files in it:
        -   CANBusProtoboard-1.0.GBL  - Gerber Bottom Layer copper
            traces
        -   CANBusProtoboard-1.0.GBO  - Gerber Bottom Silkscreen
        -   CANBusProtoboard-1.0.GBS  - Gerber Bottom Soldermask
        -   CANBusProtoboard-1.0.GTL  - Gerber Top Layer copper traces
        -   CANBusProtoboard-1.0.GTO  - Gerber Top Silkscreen
        -   CANBusProtoboard-1.0.GTS  - Gerber Top Soldermask
        -   CANBusProtoboard-1.0.TXT  - Excellon Drill File (for all the
            holes that need to be drilled into your board)
    -   the above \"gerber and drill\" files are collected and gzip\'d
        into
        -   CANBusProtoboard-1.0.gerbers.tar.gz
    -   while the Eagle files
        -   CANBusProtoboard-1.0.sch and
        -   CANBusProtoboard-1.0.brd
    -   are put in
        -   CANBusProtoboard-1.0.eagle.tar
3.  If you are using BatchPCB:
    -   You can now use [your BatchPCB
        account](http://batchpcb.com/index.php/AccountHome/PcbDesign) to
        (Upload a New Design). I use the basename of my project, with a
        version number, for the name of the design, e.g., \"CANBus
        Protoboard 1.0\" I then (Browse) to the eagle directory created
        by the **makeboard** script, then select the
        \...gerbers.tar.gz\" file. Click (continue) a couple more times
        and your board design will be uploaded and validated by
        BatchPCB\'s automated system.
    -   If it passes, you can then order 1 or 100 or more of your
        board - though I\'d recommend you start simple so you don\'t
        waste money making coasters :-)
4.  If you are using Seeed Studio\'s Fusion product:
    -   Submit an order for one or more Seeed Fusion products (one per
        board design\...).
    -   When you get a confirmation email, respond with a tar file
        attachment with the order number in the Subject: line
5.  Finally, you can upload the \...eagle.tar file to your blog or
    website so that others can build on your efforts as they explore the
    world of making their own boards.
