# NOTE: This page will be getting rewritten over the next few days.
## For now, the easiest way to configure WIFI is by pressing the F12 button for the MiSTer menu, go to the scripts folder and run the WIFI script.
## Better instructions coming soon!!

Starting from Release 20180115 MiSTer supports some WiFi USB modules.

### Enable WiFi connection
* locate the file **linux/_wpa_supplicant.conf** (example: /media/fat/linux/_wpa_supplicant.conf)
* open in text editor **supporting Linux/Unix** line endings (for example Notepad++)
* replace **put_your_SSID_here** with your actual WiFi network name and **put_your_password_here** with your WiFi password.
* sometimes you need to change the country code from TW to yours.
* rename **_wpa_supplicant.conf** to **wpa_supplicant.conf**
* reboot the MiSTer

In Menu core you will see WiFi icon when WiFi is connected.

## WiFi USB dongles Confirmed to work (running command "lsusb" on linux will show if USB ID matches)
* ASUS USB AC53 nano rev A1.
* CanaKit USB WiFi dongle - Works out of box (USB ID: 148f:5370, driver: rt2800usb, firmware: rt2870.bin)
* Comfast CF-812AC (USB ID 0bda:b812, 5GHz capable, works out of the box)
* D-Link DWA-171 HWVer: A1. (NOTE! D-Link DWA-171 HWVer: C1 / USB ID 0bda:1a2b does NOT work out of the box)
* Edimax EW-7612UAn V2
* Edimax EW-7811UN (USB ID 7392:7811)
* Edimax EW-7822ULC (USB ID 7392:b822, 5ghz capable)
* Netgear A6100 (USB ID 0846:9052, 5GHz capable, works out of the box, driver: rtl8821au)
* TP-LINK TL-WN823N V2 (needs copy rtl8192eu_nic.bin to /lib/firmware/rtlwifi)

Some WiFi firmwares can be found here: https://github.com/wkennington/linux-firmware

## Compiling and installing custom WiFi drivers

Instructions for rtl8188fu based adapters (like the Zapo RTL8188 USB stick) can be read here:
 
[MiSTer custom WiFi driver compilation](MISTER-CUSTOM-WIFI-DRIVER-COMPILATION-GUIDE)

Steps can be adapted for other WiFi adapters.