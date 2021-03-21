The MiSTer menu can be customized in a number of ways.

eg You can add a cool font, or change the background image for the main menu.


# To change the default font

Create a /media/fat/fonts folder on your SD card.


Next download the fonts from here - [MiSTer Fonts](https://github.com/MiSTer-devel/Fonts_MiSTer)

Copy the pf files downloaded from that url to the /media/fat/fonts folder


Next edit /media/fat/MiSTer.ini


Find the 

font= line, and edit to use a new font.  Be careful not to add a / before the font folder!


eg

If you want to use the C64 font - change the font line to 

font=fonts/Computer_C64.pf



# To add a background image


Find a suitable png or jpg file that you like

Copy your desired image to /media/fat/menu.jpg or /media/fat/menu.png (as appropriate)

reboot


Press F1 once rebooted into MiSTer to select your background.



# To use multiple background images


There is also a way to have MiSTer choose from a selection of wallpaper images at random. On the root of your micro SD card (`/media/fat`), you can create the following folder:

`wallpapers`

Remove the `menu.jpg`/`menu.png` file (if present) from the root of the micro SD card. Populate the wallpapers folder with your desired images. Press `F1` to cycle through the included default images until you see one of the custom wallpaper images you have added, then leave it on that image. On the next restart, a different image will be chosen at random.

You can also create the following additional folders:

`wallpapers_alt_1`
`wallpapers_alt_2`
`wallpapers_alt_3`

MiSTer supports [up to three additional configuration profiles](https://github.com/MiSTer-devel/Main_MiSTer/wiki/Configuration-Files#switching-ini-files-on-the-fly). The active `MiSTer.ini` or `MiSTer_alt_*.ini` file will determine from which folder the images are selected. If any of your configuration profiles use different resolutions, you can populate the corresponding wallpapers folders with only images of that profile's resolution. Each of these folders can have completely unique multiple images, or you can place just one image in each folder to have greater control over which background is used for certain configuration profiles.