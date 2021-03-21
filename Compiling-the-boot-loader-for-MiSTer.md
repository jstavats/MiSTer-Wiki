There are few reasons why you would want to modify, build, and install the u-boot boot loader used by MiSTer.  It is assumed anyone undertaking this is aware of the risks and prepared to deal with them.  

_Disclaimer: Although unlikely, misconfiguring the boot loader could lead to hardware damage._

Realistically, in the worst case, you will have to use a computer to reinstall the original u-boot image on the appropriate partition of your SD card.

__Why would you want to build a custom u-boot?__  The most common scenario is that there is some hardware peripheral or feature of the Altera Cyclone V SoC FPGA that you seek to enable, possibly for experimentation or adding a custom hardware capability to your MiSTer.  In short, the ''why'' is left to the reader, and the ''how'' is addressed below.

## High-level steps for building a MiSTer-compatible u-boot

Building a working u-boot image seems to requires an ARM cross-compilation toolchain with GCC version 4 or 5 (earlier may work but was not tested).  __Warning: In my experience, using a later version of GCC produces a u-boot image that is unable to reboot without a power cycle.__

1. Set up a cross-compilation environment as documented in the instructions for [Compiling the Linux Kernel for MiSTer](Compiling-the-Linux-kernel-for-MiSTer), but do not download or install the ARM toolchain.

2. I suggest downloading and installing the Linaro 5.5-2017.10 toolchain, as it is the latest version that I found works properly. The current stock u-boot image distributed with MiSTer was compiled with GCC 4.8, so Linaro 4.9-2017.01 is another reasonable choice and still available for download as a binary at the time of this writing.
```
wget -c https://releases.linaro.org/components/toolchain/binaries/5.5-2017.10/arm-linux-gnueabihf/gcc-linaro-5.5.0-2017.10-x86_64_arm-linux-gnueabihf.tar.xz
```

3. Continue with the steps for installing the toolchain detailed in [Compiling the Linux Kernel for MiSTer](Compiling-the-Linux-kernel-for-MiSTer), substituting "5.5-2017.10" for the Linaro version.

4. The u-boot source is available in the https://github.com/MiSTer-devel/u-boot_MiSTer repository (--depth=1 clones only the recent version, slimming down the download; omit this if you would like the full commit history):
```
git clone --depth=1 https://github.com/MiSTer-devel/u-boot_MiSTer
```

5. Compile the source:
```
cd u-boot_MiSTer
make MiSTer_defconfig
make -j6
```

6. Copy the u-boot image over to your MiSTer device.  Note that the file must be copied to `linux/uboot.img` on your SD card. I suggest making a backup copy of the original `linux/uboot.img`.  For example, if you are using `scp`:
```
scp root@[IP address of your MiSTer]:/media/fat/linux/uboot.img uboot.img.orig
scp u-boot-with-spl.sfp root@[IP address of your MiSTer]:/media/fat/linux/uboot.img
``` 

7. Install the u-boot image on the appropriate partition of your SD card:
```
ssh root@[IP address of your MiSTer]
cd /media/fat/linux
./updateboot
```

8. Power cycle your MiSTer (as opposed to a warm reboot).