MiSTer supports many different USB input devices. 

Any USB HID compatible device will be recognized.

For recommendations you can refer to [Selecting Input Devices](Selecting-Input-Devices).



## Keyboard
A keyboard can emulate other input devices, _so basically it is enough to control all cores._

MiSTer keyboard features a flexible key re-mapping function, mouse and gamepad emulation, and more. 

See [Keyboard](Keyboard) for details

## Mouse
MiSTer supports up to 3 buttons (exact number of mouse buttons is core-dependent).

Most USB wired and wireless mice, trackballs and touchpads will work. 

## Joystick and gamepads

MiSTer has a powerful set of features for USB gaming controllers:

* [Up to 6 player support](#joystick-player-assignment)
* [Button mapping options](#usb-joystick-mapping)
* [Auto Fire](#auto-fire)
* [Mouse emulation from joystick](#mouseemu)
* [Debugging options](#debugging-controllers)


### Joystick player assignment
Up to 6 player controllers are supported (depending on core):
* After a core starts, press a button on any connected controller to make it the P1 gamepad/joystick
* Press a button on a second controller to make it the P2 joystick (if supported by core)
* Keep going for assigning P3, P4, etc.
* To remap, just clear all assignments by restarting the core.

### USB Joystick mapping
USB joysticks, gamepads, and keyboards need to be defined in the central menu before use in any core.
Please refer to [Main Joystick Mapping](Main-Joystick-Mapping)

### Auto fire
Any defined button (except d-pad) supports **auto fire** feature. To activate auto fire, press and keep desired button and then quickly press the button defined as "BUTTON OSD"(for joystick) or "KBD TOGGLE"(for keyboard). To deactivate auto fire, repeat the the same procedure.

Auto fire provides 50ms-1000ms rates. To choose the speed, press and keep one of direction on d-pad and then quickly press the button defined as "BUTTON OSD"(for joystick) or "KBD TOGGLE"(for keyboard).

### Mouse emulation
Joystick can emulate mouse if required button **"Mouse Emu"** has been defined in default joystick definition (Menu core).
Hold **"Mouse Emu"** button and **"Alt/M"**, **Mouse Left/Right/Middle Btn** will emulate the mouse functions. Also defined analog stick for mouse will be switched to pointer functions. Press **"BUTTON OSD"** while holding **"Mouse Emu"** to toggle mouse emulation permanently. In permanent mouse emulation "Mouse Emu" button becomes a **sniper button** (smaller pointer movements). Only buttons defined for mouse emulation will be switched. Other joystick buttons will continue to act as joystick buttons. Thus, if your game pad has many buttons, you can have both mouse and joystick in one game pad at the same time (useful for some games, like Walker on Amiga).

### Debugging controllers
* Joystick actions can be viewed in [serial console](Console-connection) while running Menu core.



## JammaSD arcade i/o board

MiSTer supports the use of a JammaSD by detecting if the pressed buttons are from player 1 or 2.  
You first have to configure player 1 in main menu (as a joypad) (and also remap it in cores if needed).  
Player 2 inputs will be auto defined, like if it was a second identical joypad.  
JammaSD support was added with a VID/PID that should be the same across all devices, but if your device has a different VID/PID, you can adjust it in the MiSTer.ini file.  
