The User Port is the port on the IO Board that has the same physical appearance as a USB 3.0 port, but it is merely using a USB 3.0 connector as a means for serial I/O communication. The port could potentially have various uses, but these are features that are currently implemented or upcoming:

## Controllers
### Implementations:
**[SNAC](https://github.com/blue212/SNAC) (Serial Native Accessory Converter)**: This essentially means that a system's original controller can be connected (on supported cores) to be used as if they were connected to the original system. This means there is absolutely no lag unless it's native to the original system. Additionally, any original accessories should be compatible within reason (this won't make your original lightguns magically work on a LCD). Currently only one controller port is supported, but (depending on the core) can be swapped between the 1st and 2nd controller port in the core's OSD.

An adapter will be required that is mostly wire-to-wire plus level shifters to translate the DE-10 Nano's 3.3V IO pins to 5V used in older system's controllers.
Currently supported cores:
* NES
* SNES

***

**BlisSTer** (available at selected stores) This is a combination of a USB hub board that also has a low-latency controller interface using the [Low-Latency API (LLAPI)](https://github.com/Kitrinx/LLAPI) designed to work with Bliss-Box adapters. These adapters will allow you connect original controllers for various systems with extremely low latency. The upside of this is that you could technically use any compatible controller with any supported core, so you could, for example, use a Genesis controller on the NES core if you really wanted to. The downside vs. SNAC is that this will mostly/only work with controllers, so multi-taps and oddball accessories will generally not be compatible with BlisSTer, and use of special [LLAPI versions](https://github.com/MiSTer-LLAPI) of the cores is required. These forked versions may not be as up-to-date as the stock cores.