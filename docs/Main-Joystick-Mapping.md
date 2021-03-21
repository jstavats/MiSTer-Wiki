Before using any controller with a MiSTer core, it must be defined in the main menu core

## MiSTer's mapping system

MiSTer has a simple three-step mapping system:

1. Define centrally a physical controller into a virtual "[MiSTer gamepad](#mister-gamepad)" (+ extras)
2. MiSTer gamepad is mapped automatically to cores<sup>1</sup>
3. If needed, you can override at any time per core (and per controller) via OSD menu

<sup>1 - Mapping of MiSTer gamepad into cores has two "flavors" of operation, chosen by INI file. More below.</sup>

## Preconfigured MiSTer mappings 

Community-created controller mappings can be found [in this repository](https://github.com/misteraddons/Mister-Input-Maps). 

They need to be extracted into SD card folder:
> /media/fat/Inputs/

Alternatively you can define your own mappings following the steps below.


## MiSTer Gamepad

The first step is to teach MiSTer to recognize your physical controller.

This is done in the menu shown at startup.

After plugging a keyboard, press F12 to show system settings and select "Define joystick buttons"

![Showing the location of the option to define buttons](https://i.imgur.com/ZcbSCHV.jpg)

MiSTer will then ask you to assign several buttons to your controller:
* Test the D-Pad and analog sticks (if any)
* Four face buttons and two shoulder buttons
* Start and Select
* OSD button or 2-button combo (to use instead of F12 on the keyboard)
* A few extra buttons for advanced functions (more below)

Here is a conceptual representation of the MiSTer Gamepad:
![MiSTer Virtual Gamepad representation](https://i.imgur.com/nrXX30Q.png)

MiSTer internally recognizes more buttons (and two analogue sticks), but the above is the minimum required to work on most cores. You can also ignore the analogue stick as long as you do not use the few cores that require it (e.g. Apple II, Atari 5200).

## From USB hardware to MiSTer Gamepad

This step is exclusively handled in the main startup menu. You can override it by re-doing a mapping from inside a core.

MiSTer uses USB HID to handle controllers. Each controller is recognized by a unique USB ID (VID:PID) and declares what it can do (does it have d-pad? how many buttons?). This information does not contain any physical information (which button is "A", where it is located...) and you may want to decide which buttons to specifically assign for each function. 

That is where you come in. MiSTer will ask you to:
* Test D-Pad and analogue sticks (effectively a joystick calibration)
* Choose what to use for directions (can be D-Pad, any analogue stick, or even buttons)

Then it will ask you to assing:
* A, B, X, Y, L, R buttons to the MiSTer gamepad (see image above)
* Start and Select buttons
* A button or a 2-button combo to open the OSD

And finally it will ask to select:
* Alternative directions (also used for mouse emulation)
* Controller buttons to use as mouse buttons (left, right, middle)
* Button to turn on mouse emu (and to use as "sniper" mouse mode)

See below for a more technical description of each step.

During the mapping you can press:
* **ESC** to cancel the mapping operation and return to menu
* **SPACE** to skip a button (that button will remain undefined)
* **ENTER** to end the mapping without mapping any further buttons (keeps maps done so far)

The screen will also display the VID:PID (the USB ID) of your controller.

![OSD menu for gamepad mapping](https://i.imgur.com/lpLownF.jpg)

### More technical details on each step 

_**Calibration**_
* **D-Pad type test** This is an important step since some USB controllers generate analog events from the D-Pad, and it that case a small calibration must be done for all directions to be recognized. Simply press the RIGHT button on D-Pad first. If it generates analog stick event, then MiSTer will ask to press DOWN as a second stage. Otherwise it will proceed to the next steps if no analog event has been detected. If you are defining keyboard keys for joystick emulation, then simply press the RIGHT arrow key and it will skip Stick 1/2 steps and jump to D-Pad keys definition.
* **Stick 1 and 2 analog axes** If your gamepad has no analog sticks then skip this step via the SPACE key. Otherwise, you need to define them for it to be calibrated and use proper analog to digital mapping. (**Note:** Some gamepads like 8bitdo M30 emulate analog stick events on DPAD, so you have to press RIGHT and DOWN for Stick 1! Skip for Stick 2). Note that these definitions have no relation to any specific mapping, it only tells to MiSTer these axes have min-0-max values with 0 as a default position and will be mapped to 2 digital buttons at the both ends. Other analog axes not defined here will be treated as 0-max with only 1 digital button.

_**Virtual D-Pad and Buttons**_
* **Right,Left,Down,Up** Virtual D-Pad directions. You can use an analog stick or even buttons if desired.
* **A,B,X,Y,L,R,Select,Start**. Basic buttons, any physical button can be assigned to these. Skip with SPACE if your physical controller is missing some buttons. 

_**Alternate layout and Mouse emulation**_
* **Right,Left,Down,Up (Mouse and Alt)** - alternative direction control. If your gamepad has analog stick, then you can assign it here. In cores this alternative control will work in parallel to the one defined in the core. So you will be able to control directions with DPAD(or whatever you've defined in core) and analog stick. Some games are good to be controlled by stick, other games are good with DPAD. These controls are used for mouse emulation as well, so if you don't have the stick (or don't want to use it), then define DPAD buttons here again. The same sticks defined here will be used for mouse emulation.
* **Mouse Left/Right/Mid Btn** - buttons for mouse emulation. If your gamepad has many buttons then you can define separate buttons for mouse only, so when in mouse emulation mode both joystick and mouse buttons will be available at the same time. On reduced gamepads you may define the same buttons used for Btn1..Btn4.
* **Mouse Emu/Sniper** - button to switch to mouse emulation. While holding it down gamepad will emulate the mouse. In permanent mouse mode (press OSD button while in temporary mouse mode) this button is used for smaller pointer steps (sniper mode).

_**System and analog stick selection**_
* **BUTTON OSD** - important button used to access OSD menu and some additional functions.
* **Stick X/Y** - analog axes. Some cores support or even require analog joystick. This allows you to define exactly which input is used for this. For gamepads this is usually the left stick.

**Note:** Keyboard can be used as joystick. So you have to define the keyboard as joystick in both Menu core and the core you want to use!

Mapping settings are specific to each device (identified by VID and PID). If you have several identical gamepads/joysticks then they will share the same button layout.

The number of button supported per core varies (up to 32). While defining buttons, you can press "SPACE" to skip (keep undefined) the button, "ESC" to cancel, and "Enter" to stop mapping  (i.e. make the rest of buttons undefined).