# Welcome to the MiSTer wiki!

You can also join us on the [Forums](http://www.misterfpga.org/) or hop onto our [Discord server](https://discord.gg/4xKVg4XVYn).


## What is it?

**MiSTer** is an open project that aims to recreate various classic **computers**, **game consoles** and **arcade machines**, using modern hardware.  It allows software and game images to run as they would on original hardware, using peripherals such as mice, keyboards, joysticks and other game controllers.

MiSTer utilizes a readily available **FPGA** board called the '**[DE10-Nano](https://github.com/MiSTer-devel/Main_MiSTer/wiki/How-to-start-with-MiSTer#1-board-de10-nano)**', which connects to your TV or monitor via **HDMI** video out.  It can additionally be expanded with various **[add-ons](https://github.com/MiSTer-devel/Main_MiSTer/wiki/How-to-start-with-MiSTer#2-usb-connection)** (such as a USB hub, SDRAM, audio and VGA out).

The MiSTer software/OS itself is **[freely downloadable](https://github.com/MiSTer-devel/Main_MiSTer/wiki/Setup-Guide#prepare-the-sd-card)**, and anyone is welcome to contribute to its development.  In fact MiSTer relies on the contributions of many developers for the various systems (known as '**cores**') it replicates.  

The MiSTer project is currently under active development, with new cores, features, and bug-fixes appearing on a regular basis.

![photo](pictures/MiSTer.jpg)

_DISCLAIMER: MiSTer is an open source project without a focus on sales. Base hardware (Terasic DE10-Nano) can be bought from major electronic component resellers and will run a few cores out of the box. No soldering is required._ 

_DISCLAIMER 2: Many cores require RAM expansion hardware, which can be assembled or bought from a few sources in the forums. The author of this project and contributors are NOT affiliated with these vendors and do not derive any income from them. Please direct any inquiries or concerns about expansion hardware to relevant third parties._

## Technical Details

MiSTer is a port of the well-known [MiST project](https://github.com/mist-devel/mist-board/wiki) to a larger field-programmable gate array (FPGA) and faster [ARM](https://en.wikipedia.org/wiki/ARM_architecture) processor. MiSTer provides modern video output through HDMI (VGA and analog audio are still available via an optional daughter board, or with third-party DACs and the direct video feature). It's based on the [**Terasic DE10-nano**](http://www.terasic.com.tw/cgi-bin/page/archive.pl?Language=English&CategoryNo=167&No=1046) board.
Here are some improvements over the MiST board:

* Altera Cyclone V SE FPGA with 110,000LE (41,500ALM) and 5,570Kbit of Block RAM.
* ARM Cortex A9 dual-core CPU at 800MHz.
* HDMI video and audio allowing connect to any modern monitor/TV.
* DDR3 1GB available for both ARM and FPGA.
* High speed ARM<->FPGA interconnect due to both being in the same chip.
* Linux on ARM provides support for many I/O devices and file systems.
* Board is mass-produced by a large manufacturer and freely available for a relatively cheap price 130USD (99USD for students/professors).

Due to a larger FPGA, bigger systems can be created than was possible on MiST. It's also possible to add more support from the ARM side. For example, TZX tape format can be parsed on ARM and then sent to the FPGA. Firmware is not limited by code size or available RAM. It's even possible to emulate some parts of system through ARM that are not available in the FPGA (resulting in a so-called hybrid emulator). 

MiSTer scales original video resolution to a standard HDMI resolution (usually 1280x720p60), so you don't need to look for some ancient monitor with VGA input supporting non-standard resolution and frame rates. For purists, analog video output is still available and it uses the system's original video resolution where possible.

## How does it work?

MiSTer adds several [daughter boards](https://github.com/MiSTer-devel/Hardware_MiSTer) to the original DE10-nano board. **You don't need to install all boards.** MiSTer starts from entry level as a bare DE10-nano board. With just one additional board (SDRAM), you will be able to use almost all cores.
* **SDRAM board** _(recommended expansion)_ – This small board plugs into the GPIO0 connector of the DE10-nano board. Whilst the DE10-nano has fast DDR3 memory, it cannot be used to emulate a retro EDO DRAM due to a high latency and shared usage from the ARM side. This SDR SDRAM on a daughter board is required for most cores to emulate a retro memory module.
* **I/O board** _(optional expansion)_ – This board plugs into the GPIO1 connector of the DE10-nano board. It provides a legacy VGA output (6 bits per component), analog audio (3.5mm phone jack), digital optical audio, buttons, and LEDs. This board is useful if you prefer VGA over HDMI or you want to put the MiSTer inside a case. This board also helps for core development; HDMI scaler code requires around twice as much time to compile, while compiling for VGA-only will speed up development. This board is not required to run most cores. Alternatively, if all you want is analog video and audio output, you can also use a compatible DAC with [Direct Video](Direct-Video) mode, so you don't need to install this board.
* **RTC board** _(optional expansion)_ – This board is plugged into the LTC connector and provides a real-time clock (RTC). You still can have a real-time clock without the board if MiSTer is connected to Internet via Ethernet. Only two cores use this feature, so it is only for enthusiasts.
* **USB hub board** _(optional expansion)_ – This board adds a 7-port USB hub that sits under the main board.

Schematics and Gerber files are available to download. Boards are considered DIY (do it yourself). There are no restrictions on how these boards are manufactured and sold, or by whom; any third party is welcome to manufacture and sell them.

## Linux?

MiSTer uses Linux for house-keeping duties such as loading data from the SD card. You might expect such a system to take considerable time to boot, but this isn't the case. The version used by MiSTer has been optimized to only take a couple of seconds to boot. Most monitors and TV require a longer time to lock on the video signal and start to display, so the result is that the MiSTer has an "instant-on" feel, like original hardware back in the day.

## More info
To learn more, or to get help with the project you can join us on the [Forums](http://www.misterfpga.org/) or our [Discord server](https://discord.gg/4xKVg4XVYn). If you would like to make changes to the wiki, please consult project maintainers before changing the list of cores in the side bar.