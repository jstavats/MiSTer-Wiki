# What USB controllers can I use with MiSTer?

Most USB controllers that support HID will work with MiSTer.

There are some known issues with some famous brands which may be worth being aware of, in order to select the best options for your own preferences. More below.

# What is the fastest USB controller I can get?

Almost any standard USB controller will work well with MiSTer, however there is a short list of excellent controllers that we can suggest based on user feedback and input lag testing:

* 8bitdo M30 2.4g connected in wired mode
* Sony DS4 in wired mode
* Hori Fighting Commander (later revisions), either PS4 or XBOX1 variant is fine; pick your favorite
* DIY USB adapter using open source firmware available [here](https://github.com/MiSTer-devel/Retro-Controllers-USB-MiSTer)

Generally speaking, while Bluetooth connected devices will work fine, you can expect the highest amount of input latency while using your controller in this way.

Please keep in mind, “high latency” controllers will add, at most, 16 ms (1/60th of a second) or one frame (or rarely, depending on the controller, 32ms) of lag, and not constantly, to your experience, which is not a lot of lag, so if you’re not the type of person who notices that, you can safely just use any decent USB controller.

For a set of devices tested with MiSTer, you can refer to [this USB controller performance data](https://docs.google.com/spreadsheets/d/1-3dIE-YI5f7Ct2qzDZZrcqRqFYCy1Y-8hjPw6PmmhE0).

Please see these article for more information about USB controller lag
* https://medium.com/@WydD/controller-input-lag-how-to-measure-it-1ebfd2c9d60
* https://inputlag.science/


# Gaming Keyboards, worth it?
High performance and expensive keyboards and mice aren't good for MiSTer. They won't give any benefits, so it's just waste of money. Also these devices have too many functions and many virtual devices cluttering input subsystem which may introduce input lag or be complete unresponsive. They may prevent other devices such as gamepads to work. So try to avoid these gaming Chrismas-Tree like keyboards and mice. Buy a simple one.**

# PS3/PS4, XBox360/XBoxOne gamepads 
These are known to have some problem with MiSTer. They have accelerometers which constantly sends the events with high rate. Analog sticks also send events even when not touched. Overall, MiSTer receives a flood of events from these controllers, and these extra events may prevent correct button definition. Games may behave incorrectly when using these controllers. 

The ideal solution today for these gamepads is to use 3rd-party receivers, such as 8bitdo retro receivers, specifically the **8Bitdo Wireless Bluetooth Adapter**. Not only it gives you wireless access, but also filters out all these unneeded events, while supporting Xbox One S/X, PS3, PS4, Wii, Switch, and 8Bitdo's own gamepads. One receiver will pair with one controller at one time. If multiple controllers are required for multiplayer games, then multiple receivers will need to be purchased.

The Grey/Orange (brick decorated) USB Adapters are functionally the same, after using the latest firmware. Gamepads may switch to different input modes using hotkeys for different functionality. Note that documentation on 8Bitdo's site doesn't specify this, but the update logs for the firmware updates does.

- X-Input mode: Hold SELECT+UP for 3 seconds.
- PSC (Playstation Classic) mode: Hold SELECT+DOWN for 3 seconds. This is useful for gamepads which are limited in buttons (12 total; DPAD counts as 4) and need to access the MiSTer OSD menu. Note that the OSD menu should not be assigned when configuring buttons in the main MiSTer menu core, as the L+R+START combination will bring up the OSD while in the cores. The combination is hard-coded in MiSTer specifically for 8Bitdo adapters. You may also lose auto-fire/mouse functionality in this mode.

Alternative 8Bitdo adapters, such as the 8Bitdo Console Retro Receiver (SNES, NES, Genesis) are always in X-Input mode when connected via microUSB.

**Bluetooth Adapters and Dongles:**  
Any off-the-shelf bluetooth dongles will work with most wireless controllers like Dualshock4, Xbox, 8Bitdo.  
See [Bluetooth](Bluetooth) for details