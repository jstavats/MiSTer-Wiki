This page contains commonly asked questions and their answers.

## Table of Contents
**General**
- [When will MiSTer support cartridges?](#when-will-mister-support-cartridges)
- [Does MiSTer have lag?](#does-mister-have-lag)
- [I've seen in the news, "Update Framework". What does that mean?](#ive-seen-in-the-news-update-framework--what-does-that-mean)

**Controllers**
- [Can I use original console controllers?](#can-i-use-original-console-controllers)
- [What about light guns?](#what-about-light-guns)
- [Any USB controller recommendations?](#any-usb-controller-recommendations)
- [What are the USB controller options?](#what-are-the-usb-controller-options)
- [Can I increase the polling rate of my USB controller to improve input latency?](h#can-i-increase-the-polling-rate-of-my-usb-controller-to-improve-input-latency)
- [Do I need the official USB Hub Add-On Board?](#do-i-need-the-official-usb-hub-add-on-board)
- [Do I need to have a USB keyboard with me to use MiSTer?](#do-i-need-to-have-a-usb-keyboard-with-me-to-use-mister)
- [How do I add a second controller to MiSTer?](#how-do-i-add-a-second-controller-to-mister)

**I/O Board**
- [Does MiSTer need an IO board?](#does-mister-need-an-io-board)
- [What are the methods for connecting controllers to the serial port of the IO add-on board?](#what-are-the-methods-for-connecting-controllers-to-the-serial-port-of-the-io-add-on-board)
- [Do I need an IO board to get analog video output to my CRT?](#do-i-need-an-io-board-to-get-analog-video-output-to-my-crt)


**Hardware**
- [Is MiSTer hard to set up? Is it really only for technical people who like to tinker?](#is-mister-hard-to-set-up--is-it-really-only-for-technical-people-who-like-to-tinker)
- [Which cores require SDRAM?](https://github.com/MiSTer-devel/Main_MiSTer/wiki/Frequently-Asked-Questions#which-cores-require-sdram)
- [Why does NES core require RAM board when Genesis does not?](#why-does-nes-core-require-ram-board-when-genesis-does-not)
- [Does my MiSTer need cooling?](#does-my-mister-need-cooling)
- [What power supply is compatible with MiSTer / DE-10 Nano?](#what-power-supply-is-compatible-with-mister--de-10-nano)
- [My MiSTer needs a case. What should I do?](#my-mister-needs-a-case--what-should-i-do)
- [What kind of screws do I use with the DE-10 Nano's 14mm long brass standoffs?](#what-kind-of-screws-do-i-use-with-the-de-10-nanos-14mm-long-brass-standoffs)


**Video**
- [How do I set up MiSTer for 1080p, shimmer free gameplay?](#how-do-i-set-up-mister-for-1080p-shimmer-free-gameplay)
- [How do I get the scanlines filters on my MiSTer to look good?](#how-do-i-get-the-scanlines-filters-on-my-mister-to-look-good)
- [I have a 4k or other higher than 1080p display. Does MiSTer support that resolution? I'd like better video scaling.](#i-have-a-4k-or-other-higher-than-1080p-display--does-mister-support-that-resolution--id-like-to-enjoy-better-video-scaling)

**Cores**
- [How does the accuracy level of various MiSTer cores compare to other FPGA options?](#how-does-the-accuracy-level-of-various-mister-cores-compare-to-other-fpga-options)
- [Will any MiSTer core ever get save states?](#will-any-mister-core-ever-get-save-states)
- [Why doesn’t this core from another repo work? Why is MiSTer so hard to use?](#why-doesnt-this-core-from-another-repo-work-why-is-mister-so-hard-to-use)
- [When is N64 core coming?](#when-is-n64-core-coming)
- [When is PlayStation core coming?](#when-is-playstation-core-coming)
- [Other cores work but I get a black screen for this one. What do I do?](#other-cores-work-but-i-get-a-black-screen-for-this-one-what-do-i-do)
- [My CD games don’t work! Help!](#my-cd-games-dont-work-help)
- [What version of the CD card bios do I need for TG16 CD?](#what-version-of-the-cd-card-bios-do-i-need-for-tg16-cd)
- [How do I make MiSTer boot into the NES core and a specific game?](#how-do-i-make-mister-boot-into-the-nes-core-and-a-specific-game)

**Other**
- [I heard the DE10-Nano board uses subsidized components. Is MiSTer doomed if that stops?](#i-heard-the-de10-nano-board-uses-subsidized-components-is-mister-doomed-if-that-stops)
- [I see a defect that some other people aren’t seeing. Should I get a different de-10 nano?](#i-see-a-defect-that-some-other-people-arent-seeing-should-i-get-a-different-de-10-nano)
- [I found some other Cyclone based dev board on sale and it has built in WiFi. Can I use it for MiSTer?](#i-found-some-other-cyclone-based-dev-board-on-sale-and-it-has-built-in-wifi-can-i-use-it-for-mister)
- [The DE-10 is rated for up to 100°C operation and it doesn’t get nearly that hot. Do I really need a fan or heatsink?](#the-de-10-is-rated-for-up-to-100c-operation-and-it-doesnt-get-nearly-that-hot--do-i-really-need-a-fan-or-heatsink)

***

##  When will MiSTer support cartridges?

MiSTer will never use physical cartridges. 

The project aims to replace the need for having original hardware for the same experience. It is also physically impractical/impossible given the number of GPIO pins available from the FPGA. 

## Does MiSTer have lag?

It depends on your setup, but it ranges from imperceptibly low to around one frame of lag.  

Zero latency is possible with certain equipment and tweaks. [See here](lag-explained) for a more detailed explanation.


## I've seen in the news, "Update Framework".  What does that mean?

The 'framework' is all the common elements between cores that handle things like IO, video scaling, etc.


***

## Can I use original console controllers?

Yes, there are many USB adapters for original console controllers. They can also be connected directly via the IO board as detailed below.

## What about light guns?

Light guns such as the NES Zapper are too timing sensitive to work over USB, but will work fine on supported cores via the IO board as detailed below. 

## Any USB controller recommendations?

Yes, please refer to [this page](Selecting-Input-Devices)

## What are the USB controller options?

Almost any controller that uses USB will work with MiSTer. You can also use a Bluetooth or 2.4ghz USB adapter for wireless. 
To reduce input latency USB may be overclocked which works with some controllers.
* [USB overclock instructions](https://github.com/MiSTer-devel/Main_MiSTer/wiki/lag-explained#input-lag)
* [USB controller performance data](https://docs.google.com/spreadsheets/d/1-3dIE-YI5f7Ct2qzDZZrcqRqFYCy1Y-8hjPw6PmmhE0)
* [USB DaemonBite](https://github.com/MickGyver/DaemonBite-Retro-Controllers-USB) (known fast controller adapters): 

## Can I increase the polling rate of my USB controller to improve input latency?

Yes you can, [see here](https://github.com/MiSTer-devel/Main_MiSTer/wiki/Lag-Explained#input-lag).

## Do I need the official USB Hub Add-On Board?

No, but you will probably want some sort of inexpensive OTG hub at least (or a regular hub with an adapter). Use a powered hub if you have many devices.

## Do I need to have a USB keyboard with me to use MiSTer?

Yes, it's a good idea to always have a USB keyboard available. Cheap wireless keyboards exist that you can use to reduce clutter.

## How do I add a second controller to MiSTer?

First setup the controller in the main menu after pluggingit in, with no core loaded.  Then you can define it in the various cores' OSD menus.

***

## Does MiSTer need an IO board?

No. The IO board is optional, but offers features that could be important for some users (audio, CRT output, etc).


## What are the methods for connecting controllers to the serial port of the IO add-on board?

SNAC (Serial Native Accessory Converter) is used for direct wiring. Supporting cores (SNES, Genesis, NES, and TG16) allow to directly connect original controllers. See [this page](https://github.com/blue212/SNAC) for details on SNAC.

## Do I need an IO board to get analog video output to my CRT?

No.  You can use an HDMI to VGA adapter to do it instead. See [Direct Video](Direct-Video).

***

## Is MiSTer hard to set up?  Is it really only for technical people who like to tinker?

No and no, but those who enjoy tinkering can get a lot extra out of their MiSTer if they wish. The minimum setup only requires attaching a memory board to a DE-10 Nano and making an SD card. See [this Setup Guide](https://github.com/MiSTer-devel/Main_MiSTer/wiki/Setup-Guide)

## Which cores require SDRAM?

You can find the updated list at the [SDRAM Requirements by core](https://github.com/MiSTer-devel/Main_MiSTer/wiki/SDRAM-Requirement-by-cores) section

## Why does NES core require RAM board when Genesis does not?
The Genesis has graphics RAM and stores data copying from the cartridge ROM. The NES does not do this, and typically accesses the ROM directly for the data which requires much tighter timings. Using the SDRAM board on the NES core allows meeting these timing requirements.

## Does my MiSTer need cooling?

Yes, you will want at least a heatsink (passive cooling). 22mm x 22mm is the ideal size. Active cooling (a fan) helps but is not strictly required.


## What power supply is compatible with MiSTer / DE-10 Nano?

The DE10 boards needs a 5V power supply with at least 2A. The connector is a coaxial "barrel" plug of 5.5 mm outer diameter and 2.1 mm inner diameter, center positive.


## My MiSTer needs a case.  What should I do?

There are two routes you can take; either make it yourself or purchase a case from an online vendor.  For DiY, you can find the necessary 3D print files online (e.g. thingiverse).

## What kind of screws do I use with the DE-10 Nano's 14mm long brass standoffs?

M3 screws, 8mm is a good length.


***

## How do I set up MiSTer for 1080p, shimmer free gameplay?

Edit mister.ini on your SD card for 1080p by setting `video_mode=8`. You will also need to use a filter in each core, which you can select in the system core menu (press OSD then 'right'). If you have no filters files, you can [download Interpolation sharp here](https://raw.githubusercontent.com/MiSTer-devel/Filters_MiSTer/master/Filters/Interpolation%20(Sharp).txt) and put it in your `/media/fat/filters/` folder.

##  How do I get the scanlines filters on my MiSTer to look good?

You will need to set the device to integer scaling for best results. Set vscale_mode=1 in mister.ini. You can play with other settings if you want the scaler to fill the screen, but scanlines won't be "perfect".

##  I have a 4k or other higher than 1080p display.  Does MiSTer support that resolution?  I'd like to enjoy better video scaling.

MiSTer can't quite reach 4k.  Edit mister.ini on your SD card to change resolutions, e.g. video_mode=12 for 1440p or video_mode=13 for 1536p (hardware maximum)


***

## How does the accuracy level of various MiSTer cores compare to other FPGA options?

Most MiSTer cores are just as, if not more accurate, as any of the other major FPGA offerings available today. Most people would not able to tell the difference between these cores and the original hardware.


## Will any MiSTer core ever get save states?

The GBA core supports save states, but is the only one right now.

Cores need to be written from scratch to support them, as was done with the GBA core. At this time there are no plan to apply this to other cores, but it may happen one day.

## Why doesn’t this core from another repo work? Why is MiSTer so hard to use?

MiSTer repo is self contained and the updater only fetches from there. Cores on other repos are not fully integrated so results vary. 
Some developers have their own discord servers or forums and you can seek support there.


## When is N64 core coming?

Probably never. There isn’t really sufficient bandwidth.

## When is PlayStation core coming?

Probably next year. Serious progress has been made by a few developers but there’s no official ETA.


##  Other cores work but I get a black screen for this one. What do I do?

Try setting vsync to 0 as your display may not support all refresh rates. (Note that this was the default setting.)

## My CD games don’t work! Help!

Unzip them. Do not zip CD games. Also put them in iso/wav/bin/img + cue format.

## What version of the CD card bios do I need for TG16 CD?
Use Japanese version 3.0. You will commonly find it with filename:
Super CD-ROM System (Japan) (v3.0).pce

## How do I make MisTer boot into the NES core and a specific game?
You need to use two different options: autobooting a core, and starting the core on a given ROM. Here is how:
In the .INI file, set `bootcore=NES_20201102.rbf` (or the specific core version you have), and comment out `;bootcore_timeout`.
Then on your NES games folder (e.g. `/media/fat/games/NES/`, copy the FDS bios as `boot0.rom`, and your .NES rom to boot as `boot1.rom`.
For more options, please refer to the [NES core documentation](https://github.com/MiSTer-devel/NES_MiSTer#installation) 


***


## I heard the DE10-Nano board uses subsidized components. Is MiSTer doomed if that stops?

De10-Nano is manufactured in very large scale for use by students and is widely available. When it reaches end of life, the open source cores and infrastructure will be ported to another widely available board.


## I see a defect that some other people aren’t seeing. Should I get a different DE-10 Nano?

No, you should report the defect and wait for a fix. There is no magical best DE-10 Nano.

##  I found some other Cyclone based dev board on sale and it has built in WiFi. Can I use it for MiSTer?

Generally, no. While it’s always possible that someone will take time to port things to other boards, the different pins and memory will mean it won’t be a straight use and unless it’s a significant upgrade, it would never gain official support.

## The DE-10 is rated for up to 100°C operation and it doesn’t get nearly that hot.  Do I really need a fan or heatsink? 

A number of complex cores (like ao486) benefit from having the chip at cooler temperatures, since heat can affect the tight timings they require. A fan is recommended to avoid any possible glitches, but you won't damage your DE10-Nano if you choose not to use one.


