Actual SDRAM Board Revisions: **XS v2.2** and **XSD v2.5**

The MiSTer SDRAM Board, although optional, is considered an essential expansion board for the DE10-Nano FPGA board. The [SDRAM is required by most cores](Cores-that-use-SDRAM) of the MiSTer platform.

## SDRAM Board Types
#### SDRAM Board Universal:
![alt text](https://image.ibb.co/iz752F/31_UBoard_Comp.png)

| | Advantages | Disadvantages |
|---|:---:|:---:|
| **Vertical** | Doesn't increase horizontal dimensions. Doesn't cover and allows better cooling for FPGA chip. Doesn't block Arduino GPIO - compatible with future or custom expansions. Easy to attach/detach. | Slightly less maximum working frequency. |
| **Horizontal Outward** | Doesn't cover and allows better cooling for FPGA chip. Doesn't block Arduino GPIO - compatible with future or custom expansions. Higher maximum working frequency. | Increases horizontal dimensions. |
| **Horizontal Inward** | Doesn't increase neither horizontal nor vertical dimensions. Higher maximum working frequency. | Blocks Arduino GPIOs - incompatible with future or custom expansions (PCB v3.2 solves this issue). Covers FPGA chip and makes cooling harder. Temperature condition is quite bad. **Not compatible with I/O board v4 and newer**.|

## Install the SDRAM Board

The SDRAM Board will be inserted into the GPIO 0 Header of the DE10-Nano Board. Three additional pins will be inserted into the Arduino header JP3

![alt text](https://image.ibb.co/cZzku5/GPIO0.jpg)

When Plugging in the SDRAM Board, make sure to support the DE10-Nano from beneath with your thumbs. Forcing in the SDRAM Board without support can bend the DE10-Nano board and permanently damage it.

![alt text](https://image.ibb.co/mYJLu5/77_F7423_E_9796_41_E6_BC61_F84005_BFE0_E7.gif)

Removing the SDRAM Board can be tricky for some GPIO connectors and just pulling won't do it sometimes. For very tight connectors, it is recommended to wiggle the SDRAM Board back and forth to remove the connectors slowly, bit-by-bit. Just pulling with force will often bend the GPIO header.

![alt text](https://image.ibb.co/hgrenQ/522_A3_D0_E_30_A6_492_D_A208_DA109_FCB9_CEE.gif)
