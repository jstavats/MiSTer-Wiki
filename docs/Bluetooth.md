# MiSTer supports Bluetooth input devices.

Supported devices: Gamepads, Keyboards, Touch pads(as a part of multifunctional keyboard). Support for mouse and standalone touch pads is unclear. Need to be tested.

Bluetooth host must be a standalone USB BT dongle. Multifunctional dongles such as WiFi+BT probably won't work. Confirmed to work dongles based on CSR8510 and BCM20702 chips. Most (if not all) BT dongles you can buy today are based on these chips.

## BT pairing dialog.
Either press and hold OSD button on I/O board for 3 seconds, or F11 key (only when OSD is active).

## Pairing for gamepads and keyboards
* Put your gamepad/keyboard into pairing mode.
* Invoke BT pairing dialog.
* MiSTer will try to find and pair the device (Keyboards require to enter pin 0000 and press enter).

## Pairing for Dualshock 3 and Sixaxis gamepads
* Connect the gamepad through USB to MiSTer.
* Press PS button and wait for lights stop to blinking and only one remain active.
* Disconnect the gamepad - lights will start to blink and then only one will remain active if succeeded.

Note: Dualshock 4 gamepad is a standard BT gamepad. So follow the first paring method.

## Notes / Troubleshooting
- Only single BT dongle is supported.
- Depends on environment condition (how many WiFi spots and active BT devices are around) you may connect more or less BT devices at the same time. In my place i could successfully connect 3 BT devices at the same time. The 4th one couldn't be connected till i turn off one of connected. Other BT dongle allowed only 2 gamepads at the same time.
- After MiSTer reboot many BT devices won't re-connect automatically. Some devices will shutdown them selves immediately, other devices need to be turned off manually then on.
- Bluetooth support was added to MiSTer_20190406. Make sure to update the Linux image, menu core and mister main. As of 2019-4-17 the [updater script](https://github.com/MiSTer-devel/Updater_script_MiSTer) doesn't update the Linux image by default, use the [SD Installer](https://github.com/MiSTer-devel/SD-Installer-Win64_MiSTer) to update the base Linux image.
- Spotty connections and difficulty pairing have been reported with non-powered USB hubs. A powered USB hub is always recommend.
- BCM20702 BT dongles may stuck in RF unresponsive state after reboot. From driver point of view device looks like working, but none of BT devices able to connect. Currently the only fix is to re-plug the dongle. CSR based dongles have no such issue.
- Console/SSH bluetooth debug commands:
    - You can SSH to the MiSTer and run `hcitool dev` to see if your BT dongle is recognized.
    - `hcitool scan` will scan and print a list of recognized Bluetooth clients.
    - `btpair` starts the same Bluetooth pairing script accessible via F11 in the MiSTer menu.
- MiSTer may not pair with Bluetooth controllers if other BT devices are present and scanning, such as Samsung Smart TVs. Turn these devices off to complete pairing; afterwards you can turn them back on.

## Wiimote
Wiimote is supported natively from Linux release 20190510. It needs to be paired just like any other BT device. You must use red sync button on the back of Wiimite (Pairing by buttons 1+2 doesn't work!). 

It's recommended to use the first Wiimote version (the one without integrated Motion Plus). This Wiimote just need to be paired once and it will automatically connect on next powering the Wiimote. Second version of Wiimote (with integrated Motion Plus, TR) is also supported but it won't be able to automatically connect later (probably due to very short time it gives to re-connect), so you have to pair it every time you want to use. 3rd party Wiimotes may or may not work, or work with problems. So it's advised to use official Wiimote.

Nunchuck and Classic Controller connected to Wiimote are supported. Mayflash Gamecube adapter for Wiimote is also supported.

To fully utilize the Wiimote you have to connect IR bar to power. You can buy a 3rd part IR bar with USB connector or modify original one to get the power from USB.

## Dolphinbar
Dolphinbar is supported at some degree. You can use modes 1 and 2 as a light gun or mouse control in some cores (Wiimote is connected to P2 joystick, so you need to select Light Gun on Joystick 2 port in the core with mouse as a trigger).  Mode 3 can be used as a traditional gamepad. Mode 4 (the main mode) is not supported due to absence of Linux drivers.

Overall Dolphinbar is quite useless and not recommended due to non-working mode 4. Native Wiimote support can do everything with traditional dummy IR bar.