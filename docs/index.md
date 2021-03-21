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

### [Donate](Donate)

## User Manual

---
* Tutorials and Reference
  * [FAQ](Frequently-Asked-Questions)
  * [Videos](External-Videos)
* Welcome to MiSTer
  * [What you will need](How-to-start-with-MiSTer)
  * [Setup Guide](Setup-Guide)
  * [INI file](Configuration-Files)
  * [Using MiSTer](Using-MiSTer)
  * [Core Status](Core-Status)
  * [Why FPGA?](Why-FPGA)
  * [What about Lag?](Lag-Explained)
  * [Discussion](http://www.MiSTerFPGA.org)
* Inputs
  * [Input devices](Input-devices)
  * [Choosing devices](Selecting-Input-Devices)
  * [Joystick mapping](Main-Joystick-Mapping)
  * [Multi Button](Multi-Button-Mapping)
  * [Bluetooth](Bluetooth)
  * [Keyboard Handling](Keyboard)
* Network Communications
  * [WiFi](WiFi-setup)
  * [FTP, SSH/SFTP](Network-access)
  * [Samba / Windows Network Shares](Samba)
  * [Internet for Amiga/ao486](Internet-and-console-connection-from-supported-cores)
  * [Console connection (Serial UART)](Console-connection)
* Extra Features
  * [Cheat Engine](Cheat-Engine)
  * [Video Filters](HDMI-Scaler-Custom-Filter-Coefficients)
  * [Audio Filters](Audio-Filters)
  * [Screenshots](Screenshot-Feature)
  * [Desktop Linux](Desktop-Linux)
  * [MIDI](USB-MIDI-with-the-Minimig-and-ao486-Cores)
  * [Customizing your setup](Customizing)
  * [Arcade Roms and MRA files](Arcade-Roms-and-MRA-files)

Add-Ons
---
* [Addons overview](Addons_Overview)
* [How to get boards?](How-to-get-your-own-addon-boards)
* [SDRAM Board](SDRAM-Board)
  * [ Assembly (DIY) ](SDRAM-Board-Assembly-(DIY))
  * [ Cores that use SDRAM ](Cores-that-use-SDRAM)
* [IO Board](IO-Board)
  * [ Assembly (DIY) ](IO-Board-Assembly-(DIY))
  * [ Secondary SD card ](Secondary-SD-card)
  * [ User Port (Serial I/O) ](User-Port-(Serial-IO))
* [Direct Video](Direct-Video)
* [Analog video output compatibility](Analog-video-output-compatibility)
* [RTC board](RTC-board)
  * [ Assembly (DIY) ](RTC-Board-Assembly-(DIY))
  * [ Core support ](Cores-supporting-RTC)
* [USB Hub](USB-Hub-daughter-board)
  * [ USB Hub Assembly (DIY) ](USB-Hub-Assembly-(DIY))
* [ADC-in (Audio/Tape input)](ADC-in-(Audio-Tape-input))
  * [ Core support ](Cores-Supporting-ADC)
* Case
  * [3D-printed (DIY)](MiSTer-case)
  * [Pi-Top (v1)](Pi-Top-v1)

FPGA Cores
---

### Computers - Classic
* [Acorn Archimedes](https://github.com/MiSTer-devel/Archie_MiSTer)
* [Acorn Atom](https://github.com/MiSTer-devel/AcornAtom_MiSTer)
* [Alice MC10](https://github.com/MiSTer-devel/AliceMC10_MiSTer)
* [Altair 8800](https://github.com/MiSTer-devel/Altair8800_Mister)
* [Amiga](https://github.com/MiSTer-devel/Minimig-AGA_MiSTer)
* [Amstrad CPC 6128](https://github.com/MiSTer-devel/Amstrad_MiSTer)
* [Amstrad PCW](https://github.com/MiSTer-devel/Amstrad-PCW_MiSTer)
* [ao486 (PC 486)](https://github.com/MiSTer-devel/ao486_MiSTer)
* [Apogee](https://github.com/MiSTer-devel/Apogee_MiSTer)
* [Apple I](https://github.com/MiSTer-devel/Apple-I_MiSTer)
* [Apple II+](https://github.com/MiSTer-devel/Apple-II_MiSTer)
* [Apple Macintosh Plus](https://github.com/MiSTer-devel/MacPlus_MiSTer)
* [Aquarius](https://github.com/MiSTer-devel/Aquarius_MISTer)
* [Atari 800XL](https://github.com/MiSTer-devel/Atari800_MiSTer)
* [Atari ST/STe](https://github.com/MiSTer-devel/AtariST_MiSTer)
* [BBC Micro B,Master](https://github.com/MiSTer-devel/BBCMicro_MiSTer)
* [BK0011M](https://github.com/MiSTer-devel/BK0011M_MiSTer)
* [Color Computer 2, Dragon 32](https://github.com/MiSTer-devel/CoCo2_MiSTer)
* [Commodore 16, Plus/4](https://github.com/MiSTer-devel/C16_MiSTer)
* [Commodore 64, Ultimax](https://github.com/MiSTer-devel/C64_MiSTer)
* [Commodore PET](https://github.com/MiSTer-devel/PET2001_MiSTer)
* [Commodore VIC-20](https://github.com/MiSTer-devel/VIC20_MiSTer)
* [DEC PDP-1](https://github.com/MiSTer-devel/PDP1_MiSTer)
* [EDSAC](https://github.com/MiSTer-devel/EDSAC_MiSTer)
* [Galaksija](https://github.com/MiSTer-devel/Galaksija_MiSTer)
* [Jupiter Ace](https://github.com/MiSTer-devel/Jupiter_MiSTer)
* [Laser 310](https://github.com/MiSTer-devel/Laser310_MiSTer)
* [MSX](https://github.com/MiSTer-devel/MSX_MiSTer)
* [MultiComp](https://github.com/MiSTer-devel/MultiComp_MiSTer)
* [Orao](https://github.com/MiSTer-devel/Orao_MiSTer)
* [Oric 1 & Atmos](https://github.com/MiSTer-devel/Oric_MiSTer)
* [SAM Coupe](https://github.com/MiSTer-devel/SAM-Coupe_MiSTer)
* [Sharp MZ Series](https://github.com/MiSTer-devel/SharpMZ_MiSTer)
* [Sinclair QL](https://github.com/MiSTer-devel/QL_MiSTer)
* [Specialist/MX](https://github.com/MiSTer-devel/Specialist_MiSTer)
* [TI-99/4A](https://github.com/MiSTer-devel/TI-99_4A_MiSTer)
* [TRS-80 Model 1](https://github.com/MiSTer-devel/TRS-80_MiSTer)
* [TSConf](https://github.com/MiSTer-devel/TSConf_MiSTer)
* [Vector 06C](https://github.com/MiSTer-devel/Vector-06C_MiSTer)
* [X68000](https://github.com/MiSTer-devel/X68000_MiSTer)
* [ZX Spectrum](https://github.com/MiSTer-devel/ZX-Spectrum_MISTer)
* [ZX Spectrum Next](https://github.com/MiSTer-devel/ZXNext_MISTer)
* [ZX81](https://github.com/MiSTer-devel/ZX81_MiSTer)

### Consoles - Classic
* [Astrocade](https://github.com/MiSTer-devel/Astrocade_MiSTer)
* [Atari 2600](https://github.com/MiSTer-devel/Atari2600_MiSTer)
* [Atari 5200](https://github.com/MiSTer-devel/Atari800_MiSTer)
* [Atari Lynx](https://github.com/MiSTer-devel/AtariLynx_MiSTer)
* [AY-3-8500](https://github.com/MiSTer-devel/AY-3-8500-MiSTer)
* [ColecoVision, SG-1000](https://github.com/MiSTer-devel/ColecoVision_MiSTer)
* [Gameboy, Gameboy Color](https://github.com/MiSTer-devel/Gameboy_MiSTer)
* [Gameboy Advance](https://github.com/MiSTer-devel/GBA_MiSTer)
* [Genesis/Megadrive](https://github.com/MiSTer-devel/Genesis_MiSTer)
* [SMS, Game Gear](https://github.com/MiSTer-devel/SMS_MiSTer)
* [MegaCD](https://github.com/MiSTer-devel/MegaCD_MiSTer)
* [NeoGeo](https://github.com/MiSTer-devel/NeoGeo_MiSTer)
* [NES](https://github.com/MiSTer-devel/NES_MiSTer)
* [Odyssey2](https://github.com/MiSTer-devel/Odyssey2_MiSTer)
* [SNES](https://github.com/MiSTer-devel/SNES_MiSTer)
* [TurboGrafx 16 / PC Engine](https://github.com/MiSTer-devel/TurboGrafx16_MiSTer)
* [Vectrex](https://github.com/MiSTer-devel/Vectrex_MiSTer)

### Other Systems
* [Arduboy](https://github.com/MiSTer-devel/Arduboy_MiSTer)
* [Chess](https://github.com/MiSTer-devel/Chess_MiSTer)
* [CHIP-8](https://github.com/MiSTer-devel/Chip8_MiSTer)
* [Epoch Galaxy II](https://github.com/MiSTer-devel/EpochGalaxy2_MiSTer)
* [Flappy Bird](https://github.com/MiSTer-devel/FlappyBird_MiSTer)
* [Game of Life](https://github.com/MiSTer-devel/Life_MiSTer)
* [TomyTronic Scramble](https://github.com/MiSTer-devel/TomyScramble_MiSTer)

### Arcade Cores
* [Arcade cores](Arcade-Cores-List)
* [Alternative versions](https://github.com/MiSTer-devel/MRA-Alternatives_MiSTer)

### Service cores
* [Boot Menu](https://github.com/MiSTer-devel/Menu_MiSTer)
* [SDRAM board test](https://github.com/MiSTer-devel/MemTest_MiSTer)
* [ADC board test](https://github.com/MiSTer-devel/ADCTest_MiSTer)

### Development
* [Template core](https://github.com/MiSTer-devel/Template_MiSTer)
* [Core porting notes](Core-porting-notes)
* [Core configuration string](Core-configuration-string)
* [USB Blaster (Debugging)](USB-Blaster-(debugging))
* [Compiling for ARM](ARM-cross-compiling)
* [Compiling the Linux Kernel for MiSTer](Compiling-the-Linux-kernel-for-MiSTer)
* [Compiling the u-boot boot loader for MiSTer](Compiling-the-boot-loader-for-MiSTer)