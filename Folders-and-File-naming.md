File names and folder names are case insensitive.
You may put .rbf files on the root of your SD card, or in their folders with names shown below.

Example of valid top level folder layout with BIOS and Bootroms in separate folder
<details><summary>Show</summary>
<p>

```
/media/fat
├── _Arcade
├── bootrom
├── cheats
├── _Computer
├── config
├── _Console
├── Filters
├── games
├── Gamma
├── linux
├── saves
├── Scripts
├── updater-pc
└── _Utility
```

</p>
</details>
Example of the files in the root of your SD card.
<details><summary>Show</summary>
<p>

```
/media/flash
├── menu.jpg
├── menu.rbf
├── MiSTer
└──MiSTer.ini
```

</p>
</details>
example of naming in the _Arcade folder
<details><summary>Show</summary>
<p>

```
_Arcade
├── 1942_20190226.rbf
├── 1943_20190509.rbf
├── Alibaba_20180313.rbf
├── Amidar_20180313.rbf
└── Arkanoid_20190227.rbf
```

</p>
</details>
You may put bootrom and bios files in the bootrom folder if you want to separate it from your games. If you want to do that use a naming convention such as this.
<details><summary>Show</summary>
<p>

```
bootrom
├── a.1942.rom
├── a.1943.rom
├── a.alibbt.rom
├── a.amidar.rom
├── a.arkanoid.rom
├── C64.rom
├── ColecoVision.rom
├── Genesis.rom
├── jtbiocom.rom
├── jtbtiger.rom
├── jtcom.rom
├── jtf1drm.rom
├── jtgng.rom
├── jtgun.rom
├── jttora.rom
├── jtvulgus.rom
├── MacPlus.rom
├── MegaCD.rom
├── Odyssey2.rom
├── QL.rom
├── SNES.rom
├── Spectrum.rom
├── TGFX16.rom
├── TI-99_4A.rom
├── TSConf.rom
├── Vectrex.rom
└── X68000.rom
```

</p>
</details>
You may put cheats in cheats with a naming convention like the games folder, like so
<details><summary>Show</summary>
<p>

```
cheats
├── GameBoy
├── Genesis
├── NES
├── SMS
├── SNES
└── TGFX16
```

</p>
</details>
You may put computers cores can be put in _Computer if you do not want to put them on the root of the SD card. The updater scripts recognizes the _Computer folder. The following is an example of file names in _Computer folder that the updater scripts will recognize.
<details><summary>Show</summary>
<p>

```
_Computer
├── Altair8800_20181113.rbf
├── Amstrad_20190923.rbf
├── ao486_20190927.rbf
├── Apogee_20190927.rbf
├── Apple-I_20190812.rbf
├── Apple-II_20191005.rbf
├── Aquarius_20190927.rbf
├── Archie_20191204.rbf
├── Atari800_20190927.rbf
├── BBCMicro_20190927.rbf
├── BK0011M_20190926.rbf
├── C16_20190924.rbf
├── C64_20190927.rbf
├── ht1080z_20190805.rbf
├── Jupiter_20190927.rbf
├── MacPlus_20190928.rbf
├── minimig_20170626.rbf
├── Minimig_20191204.rbf
├── MSX_20190928.rbf
├── MultiComp_20180629.rbf
├── ORAO_20181230.rbf
├── PDP1_20190101.rbf
├── PET2001_20191117.rbf
├── QL_20190928.rbf
├── SAMCoupe_20190928.rbf
├── SharpMZ_20180926.rbf
├── Specialist_20190926.rbf
├── Ti994a_20191020.rbf
├── TSConf_20190928.rbf
├── Vector-06C_20190926.rbf
├── VIC20_20190927.rbf
├── X68000_20171103.rbf
├── ZX81_20190928.rbf
└── ZX-Spectrum_20191116.rbf
```

</p>
</details>
The following is an example of naming convention in the config folder
<details><summary>Show</summary>
<p>

```
config
├── A.GnG_scaler.cfg
├── Genesis.CFG
├── inputs
├── MENU.CFG
├── NES_scaler.cfg
├── SNES_scaler.cfg
└── TGFX16_scaler.cfg
```

</p>
</details>
You may put console cores can be put in _Console if you do not want to put them on the root of the SD card. The updater scripts recognizes the _Console folder. The following is an example of file names in the _Console folder that the updater scripts will recognize.
<details><summary>Show</summary>
<p>

```
_Console
├── Astrocade_20190927.rbf
├── Atari2600_20190927.rbf
├── Atari5200_20190927.rbf
├── ColecoVision_20190927.rbf
├── Gameboy_20190929.rbf
├── GBA_20191204.rbf
├── Genesis_20191117.rbf
├── MegaCD_20191205.rbf
├── NeoGeo_20191205.rbf
├── NES_20191117.rbf
├── Odyssey2_20181221.rbf
├── Pong_20191006.rbf
├── SMS_20190928.rbf
├── SNES_20191117.rbf
├── TurboGrafx16_20190928.rbf
└── Vectrex_20190928.rbf
```

</p>
</details>
The following is an example layout of the Filters folder
<details><summary>Show</summary>
<p>

```
_Filters
├── Interpolation (Sharp).txt
├── LCD Color (Gameboy Color).txt
├── LCD Effects
├── LCD Monochrome (Gameboy).txt
├── Misc
├── No Interpolation.txt
├── Normal Upscaling
├── Scanlines (Bright)
├── Scanlines (Bright Sharp).txt
├── Scanlines (Bright Soft).txt
├── Scanlines (Sharp).txt
├── Scanlines (Soft).txt
├── Scanlines (Vertical)
├── SNES Interpolation (Sharp).txt
├── SNES Specific
├── Vertical Scanlines (Sharp).txt
└── Vertical Scanlines (Soft).txt
```

</p>
</details>
You may put games in games inside a subfolder for each core. You may also but BIOS files in the same folder as the ROMs for each system and name it boot.rom, if the core does not use a BIOS file you can rename a ROM file to boot.rom and it will autostart with that ROM. You may also just put BIOS or autostart ROMs in its own folder, see above for naming. Here is an example of folder names inside the games folder
<details><summary>Show</summary>
<p>

```
games
├── Altair8800
├── Amiga
├── Amstrad
├── ao486
├── APOGEE
├── Apple-I
├── Apple-II
├── AQUARIUS
├── ARCHIE
├── Astrocade
├── ATARI2600
├── ATARI5200
├── ATARI800
├── BBCMicro
├── BK0011M
├── C16
├── C64
├── Coleco
├── Doom
├── GAMEBOY
├── GBA
├── Genesis
├── HT1080Z
├── Jupiter
├── MACPLUS
├── MegaCD
├── MSX
├── MultiComp
├── NeoGeo
├── NES
├── ODYSSEY2
├── ORAO
├── PDP1
├── PET2001
├── QL
├── SAMCOUPE
├── SHARP MZ SERIES
├── SMS
├── SNES
├── Spectrum
├── SPMX
├── TGFX16
├── TI-99_4A
├── TSConf
├── VECTOR06
├── VECTREX
├── VIC20
├── X68000
└── ZX81
```

</p>
</details>
Example files for the Gamma folder
<details><summary>Show</summary>
<p>

```
Gamma
├── Poly 2.3.txt
├── Poly 2.4.txt
├── Poly 2.5.txt
├── Poly 2.6.txt
├── Poly 2.7.txt
├── Poly 2.8.txt
├── Poly 2.9.txt
├── Poly 3.0.txt
├── Poly_Gamma
└── Pure_Gamma
```

</p>
</details>
Example files in the linux folder, these files are case sensitive. 
<details><summary>Show</summary>
<p>

```
linux
├── bluetooth
├── linux.img
├── MidiLink.INI
├── mt32-rom-data
├── ppp_options
├── _samba.sh
├── soundfonts
├── uboot.img
├── unrar-nonfree
├── updateboot
├── _wpa_supplicant.conf
├── wpa_supplicant.conf
└── zImage_dtb
```

</p>
</details>
Example folder names inside the saves folder, they use the same names as the games folder
<details><summary>Show</summary>
<p>

```
saves
├── GBA
├── Genesis
├── NES
├── SMS
└── SNES
```

</p>
</details>
Example view of the Scripts folder
<details><summary>Show</summary>
<p>

```
Scripts
├── bluetooth_pair.sh
├── build_mame_roms.sh
├── change_ini_properties.sh.inc
├── change_ini_property.sh.inc
├── cifs_mount.sh
├── cifs_umount.sh
├── core_manager.sh
├── firewall_off.sh
├── firewall_on.sh
├── ftp_off.sh
├── ftp_on.sh
├── gdrive_config_download.sh
├── gdrive_config_upload.sh
├── gdrive_saves_download.sh
├── gdrive_saves_upload.sh
├── gdrive.sh.inc
├── ini_settings.sh
├── mac_address_change.sh
├── rclone_config_download.sh
├── rclone_config_upload.sh
├── rclone_saves_download.sh
├── rclone_saves_upload.sh
├── rclone.sh.inc
├── reboot.sh
├── rtc.sh
├── samba_off.sh
├── samba_on.sh
├── security_fixes.sh
├── soundfont_install.sh
├── ssh_off.sh
├── ssh_on.sh
├── timezone.sh
├── update.ini
├── update.sh
├── video_mode_ntsc_pal_off.sh
├── video_mode_ntsc_pal_on.sh
├── video_settings_compatibility.sh
├── video_settings_optimal.sh
└── wifi.sh
```

</p>
</details>
If you want to connect your SD card to a computer and run the Updater, without connecting your MiSTer device to the internet. You can get the updater-pc tool (for Windows and Linux). You can run the bat file in Windows or the sh file in Linux. The only file that is really needed if you are on Linux and dont need Windows is the curl-ca-bundle.crt and the update-linux.sh files. The rest of the files (except the license folder) are for windows functionallity. Example view of the updater-pc folder:
<details><summary>Show</summary>
<p>

```
updater-pc
├── awk
├── bash.exe
├── cat.exe
├── curl-ca-bundle.crt
├── curl.exe
├── cygattr-1.dll
├── cygbz2-1.dll
├── cyggcc_s-1.dll
├── cyggmp-10.dll
├── cygiconv-2.dll
├── cygintl-8.dll
├── cygmpfr-6.dll
├── cygncursesw-10.dll
├── cygpcre-1.dll
├── cygreadline7.dll
├── cygwin1.dll
├── date.exe
├── gawk.exe
├── grep.exe
├── head.exe
├── libcurl.dll
├── licenses
├── md5sum.exe
├── mkdir.exe
├── mktemp.exe
├── mv.exe
├── ps.exe
├── rm.exe
├── sed.exe
├── sync.exe
├── touch.exe
├── tr.exe
├── unzip.exe
├── update-linux.sh
└── update-win.bat
```

</p>
</details>
You may put utility cores can be put in _Utility if you do not want to put them on the root of the SD card. The updater scripts recognizes the _Utility folder. The following is an example of file names in _Utility folder that the updater scripts will recognize.
<details><summary>Show</summary>
<p>

```
_Utility
└── memtest_20190920.rbf
```

</p>
</details>