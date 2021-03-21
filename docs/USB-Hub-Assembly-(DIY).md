## NOTE
This page is for reference only. It may not be up to date. It may not include the BOM for latest PCB version. You need to check the schematic and required components yourself!

### 1. [Order PCB](https://www.pcbway.com/setinvite.aspx?inviteid=43024)

  * [Quick order of USB Hub v2.1](https://www.pcbway.com/project/shareproject/7_port_USB_Hub_v2_1_for_MiSTer.html)

USB hub can be connected to DE10-nano with following options:
  * Option 1: [Quick order of USB Bridge with non-name USB connectors](https://www.pcbway.com/project/shareproject/USB_Bridge_board_for_MiSTer.html)
  * Option 2: [Quick order of USB Bridge with GCT's USB3150 connectors](https://www.pcbway.com/project/shareproject/USB_Bridge_with_USB3150_connectors_for_MiSTer.html)
  * Option 3: [Quick order of USB Bracket with L-shaped connector](https://www.pcbway.com/project/shareproject/USB_Bracket_board_for_MiSTer_v1_1.html)

#### PCB Layout (Gerber Files)
Check the MiSTer hardware repository for the most recent PCB files: [MiSTer_Hardware](https://github.com/MiSTer-devel/Hardware_MiSTer)


------

### 2. Order Components

This is a general overview of the components, including reference parts that were successfully used to assemble a MiSTer USB Hub <b>version 1.0</b>.

| Name | Component | Package | Value | Reference Parts |
|---|---|:---:|:---:|---|
| U1 | Terminus Tech FE2.1 USB 2.0 High Speed 7-Port Hub | LQFP-48 | - | [Terminus Tech FE2.1](https://lcsc.com/product-detail/USB_FE2-1_C39693.html) |
| X1 | Crystal | SMD-5032_2P | 12MHz, ±20ppm, 20pF | [TXC Corp 7A1209](https://lcsc.com/product-detail/SMD-Crystals_XTAL-G5032-2-12M-20pF-20ppm-20-70_C90883.html) or [Yangxing Tech X503212MSB2GI ](https://lcsc.com/product-detail/SMD-Crystals_YSX530GA-12MHZ-20PF-10PPM-40-85_C112573.html) |
| C1, C3, C6, C7 to C13 (10) | Capacitor (Ceramic) | 0805 | 10uF | [Samsung](https://lcsc.com/product-detail/Multilayer-Ceramic-Capacitors-MLCC-SMD-SMT_SAMSUNG_CL21A106KPFNNNE_10uF-106-10-10V_C17024.html) |
| C2, C4, C5 (3) | Capacitor (Ceramic) | 0805 | 0.1uF | [YAGEO](https://lcsc.com/product-detail/Multilayer-Ceramic-Capacitors-MLCC-SMD-SMT_100nF-104-10-50V_C49678.html) |
| R1 | Resistor 1% 1/8W | 0805 | 47K | [RALEC](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_47KR-4702-1_C104345.html) |
| R2 | Resistor 1% 1/8W | 0805 | 100k | [YAGEO](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_100KR-1003-1_C96346.html) |
| R3 | Resistor 1% 1/8W | 0805 | 2.7K | [RALEC](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_2-7KR-2701-1_C104167.html) |
| R4 to R11 (8) | Resistor 5% 1/8W | 0805 | 510 | [YAGEO](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_510R-510R-1_C114563.html) |
| USB1 to USB7 (7) | USB A/F 90° | USB-M-41 | - | [USB Connectors USB-M-41](https://lcsc.com/product-detail/USB-Connectors_USB-A-F-900-No-back-cover-straight-foot-Copper-shell-Not-high-temperature_C5393.html) |
| LED1 to LED7 (7) | LED | 0805 | Green | [Lite-On](https://lcsc.com/product-detail/Light-Emitting-Diodes-LED_SMD-green_C125090.html) |
| LED8 | LED | 0805 | Red | [Everlight Elec](https://lcsc.com/product-detail/Light-Emitting-Diodes-LED_Red-LED-appearance-white-SMD_C142306.html) |
| J1 | DC Socket | - | - | [GANGYUAN DC-470-2.0GP](https://lcsc.com/product-detail/Power-Connectors_GANGYUAN-DC-470-2-0GP_C194406.html) |
| J2 | MicroUSB | - | - | [Jing EE Co.](https://lcsc.com/product-detail/USB-Connectors_Jing-Extension-of-the-Electronic-Co-LCSC-micro-5PAll-posts-are-not-guided-Flat-welding-High-temperature_C40942.html) or [Korean Hroparts Elec](https://lcsc.com/product-detail/Micro-USB-Connectors_Korean-Hroparts-Elec-U-F-M5SS-W-1_C145783.html) |

* All components except FE2.1 are pretty generic and can be replaced by wide range of other components with the same values and compatible footprints.
* Use LEDs with no more than 40mcd brightness - otherwise it will hurt the eyes.