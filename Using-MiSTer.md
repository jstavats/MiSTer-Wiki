So, you've got your MiSTer and followed the [Setup Guide](https://github.com/MiSTer-devel/Main_MiSTer/wiki/Setup-Guide), now what?

Let's get you more familiar with what you can do!

## Important Hotkeys to Remember

* F12 - Brings up the Menu in any Core.
* ALT + F12 - Brings up the Select Core Menu.
* F1 - Changes the background.
* F11 - Bluetooth pairing menu (for supported [BT adapters](./Bluetooth))
* F9 - Linux Terminal/Command Line interface (Press F12 to switch back to the MiSTer menu)
* Left Shift + Left Ctrl + Left Alt + Right Alt - Reboot
* Windows + Print Screen - Take a Screenshot (automatically stored in `/screenshots/`)

## Getting Started

You'll need a USB keyboard to start and a wired internet connection is highly recommended.

Plug in the USB keyboard and your internet cable, and then power on the MiSTer. The red, orange and green led lights should start pulsing, and you should see the MiSTer menu onscreen after a second or two.

## Downloading the Updater Script - update.sh

If you used the recommended setup method for your MicroSD from the Setup Guide, then your MicroSD already has the update.sh script in the `/scripts/` folder. That means you can ignore this section.

If you didn't use the recommended method of installing to your MicroSD then we need to download the script from Github:
  
1. Press F9 to bring up the Linux prompt.  
2. Type "root" for the username and press enter, and then type "1" for the password and press enter.
3. Type `cd /media/fat/Scripts/` and press to go into the Scripts directory. If you get a message that says the directory is not found, then make the directory with `mkdir /media/fat/Scripts/` to get around this, and then do the first line again.
4. Download the update script with `wget --no-check-certificate https://raw.githubusercontent.com/MiSTer-devel/Updater_script_MiSTer/master/update.sh -O update.sh` and press enter.
5. Once it's complete, type `exit` and press enter. If the menu and interface you saw when you first booted your MiSTer doesn't come up, then press F12.

That will download the updater for you in the correct folder. We only need to download that script once. Once its installed, you can simply run the updater from the Scripts menu. We can now update the system from within MiSTer. 

Tip - Press F12 to bring up the System Menu (if you press F12 again, it will show the core menu). Use the up and down arrow keys and enter to navigate the menu.

## Fixing missing certs

If you are unable to wget as instructed above, this might be because you are missing security certificate files. The default system comes with no security certificate files, which is a bit annoying, as you need to add --no-check-certificate on wget to download anything HTTPS. Lets fix that:

1. Open the linux terminal/command prompt with F9, use `root` as your username and `1` as your password.
2. Type `cd /etc/ssl/certs` and press enter.
3. Type `wget --no-check-certificate https://curl.haxx.se/ca/cacert.pem` and press enter

Assuming it downloaded correctly, you can _now_ use wget as nature intended!

## Updating our system

Simply press F12 once or twice, until you see an option that says "Scripts" and select it. There will be a warning, make sure you read and understand this. Select "yes" and press enter to continue, and select "update" and press enter to begin your first update. This will download all of the latest releases of the official cores, scripts, and other files so you can start using your MiSTer.
  
MiSTer cores are regularly updated - sometimes daily, so run "update" regularly!

Ok, you're updated, now what?

## File Transfer Setup Summary

Now you need to setup your MiSTer to receive files. Why, you may ask? You don't want to have to remove and put in the MicroSD every time you want to send ROMs to it do you? That can wear out the DE-10 Nano's MicroSD slot.

There are multiple methods of transferring files to the MiSTer. FTP can be turned on with the FTP script, so the MiSTer can serve as an FTP server waiting for an FTP client like FileZilla to connect to it. If SSH is turned on (using the ssh script that the updater should have downloaded), you can use a file transfer client capable of sending files via the SCP protocol like WinSCP. If you [turn on your MiSTer's Samba Server](https://github.com/MiSTer-devel/Main_MiSTer/wiki/Samba), then you can open up the MiSTer's storage directly from Windows File Explorer by typing `\\mister` in the address bar and pressing enter.

**Important note:** 
When you are connecting via SSH or using the linux terminal from the MiSTer itself, the MiSTer "root" directory that is often brought up in this wiki is located in `/media/fat/`. So if the wiki refers to the `/games/` folder, that means on the MiSTer that is located in `/media/fat/games/`. If you are reading the MicroSD on your Windows PC with an adapter, or are connecting via SAMBA, then you will start in this root MiSTer folder `/media/fat` and not be able to go up any levels. This is normal.

## Transferring ROMs

Each MiSTer core has a different location that it looks to for roms by default, which resides in the `/games/` folder. These are usually explained in the respective core's README file in the github repo. They typically are named after the core, such as:

`/games/Genesis/`  
`/games/MegaCD/`  
`/games/C64/`

You'll want to start copying the appropriate file backups of your cartridges/discs/cd's - i.e. roms to the appropriate locations for the core.

Some cores require boot.rom's and bios.roms, and other kinds of prerequisite files placed in the `/games/$CORE/...` folder for that core. For instance, the MegaCD core requires a Sega CD BIOS to work, and it would be placed here:

`/games/MegaCD/cd_bios.rom`

## Configure Inputs

If you are using a usb gamepad or something similar, you will need to configure your input mapping. Press F12 once or twice until you see an option to `Define joystick buttons`, and select that option. Follow the on-screen prompts, skip anything that isn't relevant to your particular controller with the spacebar or the addon board's user button. If you make a mistake, don't worry, you can start over from the beginning. 

For more details on how to configure your joysticks: https://github.com/MiSTer-devel/Main_MiSTer/wiki/Main-Joystick-Mapping

## Play The Game!

Now you are likely ready to try and play a game. Use the main menu to navigate to the core you have already transferred the necessary roms and bios files to the core's games folder, and select the game you want to play, and enjoy your new FPGA-based gaming experience! :)