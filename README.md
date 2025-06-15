# PanasonicQ_HDMI
This repository contains the full PCB source (made in altium) and gerbers for a drop-in HDMI replacement for the Panasonic Q Gamecube Digital port.
The design is based on Steven Taffs Shuriken Video schematic drawing and as such has inherited the name in the schematic, officially named Shuriken Video Panasonic Q.

This is the ONLY true drop-in replacement for the digital port that doesn't require any additional mounting hardware, 
it will mount directly on the original metal bracket and plug into the original flat flex cable.

The 3D print works as a test-fit but will not fit without modification in the complete assembly. I'm very new to 3D printing and designing parts so I advise not printing it yet, or making your own modifications to it as it's not what I'd consider 'final' just yet!

Since the project revolves around being primarily aimed toward DIY, I made sure each of the components can be hand-soldered by an average DIY-er. 
No BGA parts ;)

Here's some example images of the finished device

![Example1](Example1.png)

![Example2](Example2.png)


## PCB Production

Testing was done using JLCPCB and as such the Gerber files are provided to their output specifications.

The design is verified to work as a 4-layer PCB and 5 can be bought at their special offer for $2.

## Bill of Materials

Are located in the BOM file in the /out folder

In case they can't be sourced, confirmed suitable replacements for the M25P40 that are pin-compatible are:

* AT25DF041B
* W25X40CLSNIG (thanks Helder)

## Programming and usage

Programming can be done via any programmer that supports the \*25 devices such as M25/AT25/AD25/GD25. It's recommended to program the spirom before soldering the FPGA in place to avoid any potential unnecessary overloading of your programmer.
CH341A is suitable for this also.

The spirom can be flashed either with the shuriken-v3 binary from GCvideo with TP4 being used for controller data, TP3 used for SP/dif audio, TP2 used for the IRReceiver and TP1 used for the IRButton 

OR

It can be flashed using the precompiled panQ binary from the /out directory. The difference here is that TP1 and TP4 have been inverted so that TP1 is the controller data and TP4 is the IRButton as well as the Enhanced DVI mode is enabled by default (for "install and forget" type installs)

## Thanks

* Original [gcvideo](https://github.com/ikorb/gcvideo) by Ingo Korb
* Steven Taffs for the original Shuriken Video schematic
* 3D print assistance By [Helder](https://heldergametech.com/) Helder's Game Tech 
* PCB+3d Print testing, feedback and tweaking [ModdestlyYours](https://www.etsy.com/shop/moddestlyyours)

## License

Creative Commons Attribution ShareAlike 4.0	CC-BY-SA-4.0
