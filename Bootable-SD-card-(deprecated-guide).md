# How to prepare the SD card.

MiSTer board requires specially formatted SD card in order to boot.
There are 2 options to prepare the SD card.

## Option 1 (Linux system).

Preferably Ubuntu 16.04.

Make sure you have sfdisk v2.26 or newer installed. (Check that with "_sfdisk --version_" command). If you get an error message that command not found - install util-linux package containing sfdisk with command "_sudo apt-get install util-linux_")

Steps to prepare the SD card:
1. Download [SD Installer](https://github.com/MiSTer-devel/SD-installer_MiSTer) repository.
2. Insert SD card into PC (you need to use USB card reader otherwise script won't work!) and find the device name of the card. Usually type lsblk in command line and find your card in the list. For example it's listed as "sdc"
3. in command line navigate to the directory where you've downloaded SD installer and type: **sudo ./create_sd.sh /dev/'dev'**, so in our case 'dev' is sdc, so command will be **sudo ./create_sd.sh /dev/sdc**

**ATTENTION: installer will remove all information from SD card, so make sure you type the correct SD card's device name!**

Installer will create required partitions and put all Linux related files. Approximately 500MB of card space will be occupied by Linux. The rest of the card will be assigned to FAT partition and left unformatted. 

4. Format the FAT partition manually. Windows will see only FAT partition, so you can format it using standard windows format utility. FAT partition can be formatted either with FAT32 or exFAT. I recommend to format with exFAT - it supports partitions >32GB and files >4GB. Choose cluster size 32KB or 64KB while formatting. Smaller cluster size will slowdown the booting and file loading.

5. Place [MiSTer](https://github.com/MiSTer-devel/Main_MiSTer/tree/master/releases) and [Menu.rbf](https://github.com/MiSTer-devel/Menu_MiSTer/tree/master/releases) binaries on FAT partition. Remove date-codes from names.

## Option 2 (Windows system)
Check guide for SD installation [here](https://github.com/MiSTer-devel/Main_MiSTer/wiki/Beginner-Setup-Guide)

***

## Notes:

* Time after time Linux part will be updated, so you need to update the SD card. Due to FAT partition hasn't touched by installer, everything on FAT partition will be left as-is (if you didn't alter the FAT partition size by other tools). So it's safe to update the Linux part on already prepared SD card.
* MiSter allows to use USB storage for cores and their data, but boots only from SD card. Thus you can use the minimal SD card image from Option 2 just to boot, and use USB storage for everything else.
* USB storage needs significantly longer time to be detected. This time required whenever you power on the board, press reset button or hard reset keyboard configuration. Once USB detected, you can reload the cores without waiting.
* Don't forget to update MiSter and menu.rbf files if you want to be up to date. SD image may not have lates MiSTer and/or menu.rbf, so update them manually after restore the image.
* As probably you've noticed, bootable SD card contains installer as well. So, you can make/repair other SD cards using DE10-nano board from console app. Just use steps from 5 of **Option 2**.

## Troubleshooting:
1. How to determine SD-card device name in Linux?

  Run _lsblk_ command. It will show all block devices in a system (All SSDs/HDDs/SD card devices).

![SD card example](http://image.ibb.co/cjdv7k/Screen_Shot_2017_06_30_at_11_52_16_AM.png)

/dev/sdb - SD card disk itself, having a single partition /dev/sdb1 on it.

You need to execute "sudo ./create_sd.sh /dev/sdb" command to execute card installation actions.

Example output:

![Output](http://preview.ibb.co/dhb9YQ/Screen_Shot_2017_06_30_at_12_00_56_PM.png)

2. How to copy FPGA bitstream file (.rbf) file into exFAT partition under Linux? I don't see any suitable partition mounted.

exFAT partitions are not auto-mounted by default, so you need to mount it first.
For Ubuntu:
* Remember partition names that installation script printed or just run _sudo fdisk -lu_ command.

![sudo fdisk -lu](http://image.ibb.co/fiB7nk/Screen_Shot_2017_06_30_at_12_07_19_PM.png)

/dev/sdb1 with Type = "W95 FAT32" is the partition needed

* Mount the partition