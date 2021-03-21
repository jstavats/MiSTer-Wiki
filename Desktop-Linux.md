Here is the release with full-featured [Desktop Linux with GUI](https://mega.nz/#!sdxw1RZB!XXPJ6Doz2uLLqYE3OlVltXKAZMvPKszssHqwSDicb6k) and [Update 20180502](https://mega.nz/#!YVgFiDLD!9HDzwoGvwwb5NUSOSeo5yl1H7MzMBMW-SIQLx2FYe1g) (custom video mode support)

Make sure you use MiSTer Linux release from 2018 Apr 7 or later.
Extract the archive to the root of MiSTer SD card FAT partition.

Desktop Linux is based on Ubuntu 16.04 with LXDE distributed by Terasic with DE10-nano board. It's light-weight linux. Frame buffer has been completely rewritten with configurable resolution and integrated scaler. Audio output is also implemented unlike original Terasic version. VGA and all MiSTer audio outputs are supported.

How it works?
If core (rbf file) has the text file with the same name, then it means MiSTer will reboot and will use additional sets of u-boot commands from that txt file. That's how alternative kernel and linux image are used.
It's not really tied to Linux only. If there will be other cores requiring special code on ARM side, then it will be run the same way. Even bare-metal projects can be loaded.

One RBF file can have several configs using RBF as a base name + additional suffix. Several configs are included in release. Video card emulated in FPGA has 2 resolutions: 
* HDMI resolution comes from the the board to HDMI and VGA.
* Linux resolution which Linux sees. It will be boxed and then up/down scaled to HDMI resolution. 

Thus Linux may have any resolutions up to 1920x1080, including non-standard ones.

All video parameters are passed as kernel parameters in config file (txt).
Parameters are:
* altvipfb.video_mode - video mode number. Same as in MiSTer.ini (including custom modes, new format). Default is 1280x720@60
* altvipfb.aspect - set to 0 if you want to stretch Linux resolution to full screen. By default aspect=1. If bgwidth or bgheight are set, then aspect ratio is ignored in favor to explicit box dimensions.
* altvipfb.width - horizontal resolution for Linux. Default is the same as HDMI resolution width.
* altvipfb.height - vertical resolution for Linux. Default is the same as HDMI resolution height.
* altvipfb.format - color format. Default is 8888 i.e. 32bit. Other possible values are 565 and 1555 - both are 16bit colors. 565 is good alternative to 8888. It requires 2 times less memory and works faster than 32bit.
* altvipfb.bgr - set to 1 if you want to swap R and B components. Usually you don't need to use this parameter. Default is 0.
* altvipfb.bgwidth - box width. Default is the same as width.
* altvipfb.bgheight - box height. Default is the same as height.

Box resolution is added around Linux resolution before up/down scaling. It's used to add horizontal/vertical fields in order to correct aspect ratio - i.e. letterboxing. By default Linux resolution will be boxed automatically, so  bgwidth/bgheight usually are not required.

Check supplied config files to see how to use the parameters. Leave other text as-is if you don't know what it does. Text file uses Linux line endings, so you need to use compatible text editor if you edit it on Windows PC.

Note:
Linux image is mounted as read-write, so avoid from turning off or reset without proper shutdown! I suggest to choose "Reboot" instead of "Shutdown" so MiSTer will reboot into MiSTer menu where you can simply turn off the power. DE10-nano board has no power off feature, so if you choose "Shutdown" it will end by black screen and it will be hard to tell if shutdown procedure is finished already or not.
Every reboot from Linux will reboot to Menu core.
