Very raw documentation to how to compile a custom WiFi driver to be used with the MiSTer Linux distribution.
Note: this is made for MiSTer Linux branch socfpga-4.19-MiSTer, future updates may need slight changes.

## Preparations
Login to MiSTer via serial console and connect your wifi stick. Use lsusb to find out your wifi stick's device ID. Eg. in my case I 
have a Zapo RTL8188 USB stick which identifies itself as VID 0x0bda PID 0xf179. Searching on the net we can found a compatible driver
at https://github.com/ulli-kroll/rtl8188fu. We need to cross-compile this for ARM.

## Compiling
Grab a fresh Ubuntu installation, install an ARM cross-compile toolchain with build essentials. 
(apt-get install gcc-arm-linux-gnueabihf build-essential)

Create a work dir, and clone the MiSTer Linux source (https://github.com/MiSTer-devel/Linux-Kernel_MiSTer)
and the WiFi driver.

In the MiSTer Linux source directory delete the .git directory (in order to avoid the + sign in the compiled module's version number)
and execute:

	make ARCH=arm mrproper && \
	make ARCH=arm MiSTer_defconfig && \
	make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- EXTRAVERSION=-socfpga-r1 modules_prepare
	
You might face compilation issues. Use Google to find out which dependency is missing in Ubuntu and repeat the above until it completes.

Next, go to the wifi driver's git directory, drop the .git directory just for sure and execute:

	make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- clean && \
	make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- KSRC=<path_to>/Linux-Kernel_MiSTer modules
	# The exact make parameters needs to be figured out from the driver, in my case the readme.md of the driver
	# told how to execute the cross compilation

## Installation
In the wifi driver's directory copy the .ko and firmware to the MiSTer SD card, put it back to your board and turn it on, then on 
serial console after login:
- copy the .ko file to /lib/modules/4.19.0-socfpga-r1/
- copy the firmware to /lib/firmware/rtlwifi (correct path looked up in the Makefile)

Execute:

	depmod -a
	modprobe rtl8188fu
	# You should not see issues here, and if you execute iwconfig the wlan0 interface shows up
	reboot

  MiSTer should connect to the network if wpa_supplicant.conf has correct values
