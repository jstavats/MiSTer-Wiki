# Keyboard
MiSTer supports keys re-mapping which is useful for reduced or localized keyboards. Key remapping is system wide, so every core will have same key map. Keep in mind it's not macro definition, so single key is remapped to another single key. Some multimedia keys generate several key codes - these keys cannot be remapped.
Each keyboard model has its own key map stored in **/media/fat/config/kbd_[VID]_[PID].map** file. To reset all keys to default state, simply delete appropriate map file. Key remapping is available through Menu core only.

### Joystick emulation
Keyboard can be switched to joystick emulation. You need to define keys used for joystick emulation the same way you did for joysticks. Auto fire is also supported the same way as for joysticks. Button defined for "KBD TOGGLE" provides a quick switch between keyboard and joystick for defined keys.

### Mouse emulation
Keyboard can be switched to mouse emulation. You need to define mouse emulation buttons in Menu core the same way as for joystick.

### Emulation switch
To switch between emulation modes press **NumLock** or **ScrLock** till desired mode is selected. 

Switching sequence is **Mouse >> Joy1 >> Joy2 >> None**

LEDs on keyboard display the emulation modes:
* Mouse emulation: NumLock LED + ScrLock LED
* Joystick 1 emulation: NumLock LED.
* Joystick 2 emulation: ScrLock LED.

### Common functional keys/combos used in cores
* **F12** - open/close OSD menu/submenu
* **Alt-F12** - quick core selection (like in Menu core).
* **LCtrl+LAlt+RAlt** - presses the "USER" button which usually is reset in emulated system.
* **LShift+LCtrl+LAlt+RAlt** - MiSTer reset (load Menu core).


### Notes:
* Some systems provide writing support which requires additional attention to how you reset/shutdown the MiSTer. MiSTer tries not to keep any pending writes and writes physically to the disk as soon as possible. Still, safer way to reset the MiSTer from core which probably was writing to disk recently is using combo **LShift+LCtrl+LAlt+RAlt** - this will flush all caches to disk before restart. Cores without write can be restarted by hard reset button or powered down without special attention.
* LCtrl+LAlt+RAlt sequence can be replaced by some other well known combos through INI file.
