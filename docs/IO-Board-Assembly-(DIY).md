## NOTES
This page is for reference only. It may not be up to date. It may not include the BOM for latest PCB version. You need to check the schematic and required components yourself!


The following section will walk you through the steps of creating your own Mister IO Board. It describes where to order all necessary parts like PCB and components. It will also give you an overview on the equipment you need and show you how to assemble the board.

![picture](pictures/IO_Board_DIY.png)

### Important Note:
I/O board has an option to provide either +5V or +3.3V through VGA PIN9. It's supposed to be used in some handmade active VGA adapters/converters. Some cables and displays have PIN9 grounded which will make short circuit if P8(VGA PWR) has jumper! It's advised not to solder P8 at all, so PIN9 won't have a power and it will be safe to connect any cable/display. Use P8 only when you are absolutely sure you need the power on PIN9.

------

### 1. Order PCB

#### Approved PCB Manufactors
  * [PCBway](https://www.pcbway.com/setinvite.aspx?inviteid=43024) - [Quick order of I/O Board v6.0](https://www.pcbway.com/project/shareproject/I_O_Board_v6_0_for_MiSTer.html)
  * [JLCPCB](https://jlcpcb.com/)
  * [OSH Park](https://oshpark.com/)

#### PCB Layout (Gerber Files) and Schematics.
Check the MiSTer hardware repository for the most recent files here : [MiSTer_Hardware](https://github.com/MiSTer-devel/Hardware_MiSTer).
<br>The Gerber Files and Schematics are in the [releases](https://github.com/MiSTer-devel/Hardware_MiSTer/tree/master/releases) folder.

------

### 2. Order Components

This is a general overview of the components, including reference parts that were successfully used to assemble a MiSTer IO Board <b>version 5.5</b>.

<em>Please refer to the [PDF](https://github.com/MiSTer-devel/Hardware_MiSTer/blob/master/releases/iobrd_5.5.pdf) for more information.</em>

| Name | Component | Package | Value | Reference Parts |
|---|---|:---:|:---:|---|
| C1, C2, C3, C4 | Capacitor (Ceramic) | 0805 | 10nF | [KEMET <br> C0805C103K5RACTU](https://www.digikey.com/products/en?keywords=399-1158-1-ND) |
| C5, C6, C8 | Capacitor (Tantalum) | 2312 | 100uF | [VISHAY <br> 293D107X96R3C2TE3](https://www.digikey.com/products/en?keywords=718-1058-1-ND) |
| C7, C9, C10, C11, C12 | Capacitor (Ceramic) | 0805 | 10uF | [KEMET <br> C0805C106K8PACTU](https://www.digikey.com/products/en?keywords=399-4925-1-ND) |
| R1, R7, R13 | Resistor 1% 1/8W | 0805 | 510 | [YAGEO <br> RC0805FR-07510RL](https://www.digikey.com/products/en?keywords=311-510CRCT-ND) |
| R2, R8, R14 | Resistor 1% 1/8W | 0805 | 1.1K | [YAGEO <br> RC0805FR-071K1L](https://www.digikey.com/products/en?keywords=311-1.10KCRCT-ND) |
| R3, R9, R15 | Resistor 1% 1/8W | 0805 | 2.2K | [YAGEO <br> RC0805FR-072K2L](https://www.digikey.com/products/en?keywords=311-2.20KCRCT-ND) |
| R4, R10, R16 | Resistor 1% 1/8W | 0805 | 4.3K | [YAGEO <br> RC0805FR-074K3L](https://www.digikey.com/products/en?keywords=311-4.30KCRCT-ND) |
| R5, R11, R17 | Resistor 1% 1/8W | 0805 | 9.1K | [YAGEO <br> RC0805FR-079K1L](https://www.digikey.com/products/en?keywords=311-9.10KCRCT-ND) |
| R6, R12, R18 | Resistor 1% 1/8W | 0805 | 18K | [YAGEO <br> RC0805FR-0718KL](https://www.digikey.com/products/en?keywords=311-18.0KCRCT-ND) |
| R19, R20, R33-38 | Resistor 5% 1/8W | 0805 | 100 | [YAGEO <br> RC0805FR-07100RL](https://www.digikey.com/products/en?keywords=311-100CRCT-ND) |
| R21, R22, R23, R32 | Resistor 5% 1/8W | 0805 | 200 | [YAGEO <br> RC0805FR-07200RL](https://www.digikey.com/products/en?keywords=311-200CRCT-ND) |
| R24, R25, R26, R27 | Resistor 5% 1/8W | 0805 | 560 | [YAGEO <br> RC0805FR-07560RL](https://www.digikey.com/products/en?keywords=311-560CRCT-ND) |
| R28, R31 | Resistor 5% 1/8W | 0805 | 10K | [YAGEO <br> RC0805FR-0710KL](https://www.digikey.com/products/en?keywords=311-10.0KCRCT-ND) |
| R29 | Resistor 5% 1/8W | 0805 | 1K | [YAGEO <br> RC0805FR-071KL](https://www.digikey.com/products/en?keywords=311-1.00KCRCT-ND) |
| R30 | Resistor 5% 1/8W | 0805 | 680 | [YAGEO <br> RC0805FR-07680RL](https://www.digikey.com/products/en?keywords=311-680CRCT-ND) |
| D1 (D2 DNI) | General Purpose Diode | SOD80 | BAV100 | [VISHAY <br> BAV100-GS08](https://www.digikey.com/products/en?keywords=BAV100-GS08CT-ND) |
| LED1 | LED Red | 5mm | - | [Hubei KENTO Elec <br> 5AR2PD08](https://lcsc.com/product-detail/Light-Emitting-Diodes-LED_f5Red_C19488.html) |
| LED2 | LED Yellow | 5mm | - | [Hubei KENTO Elec <br> C54170](https://lcsc.com/product-detail/Light-Emitting-Diodes-LED_f5Short-legs-Round-with-edge-Bright-yellow-hair-yellow-Bagged-RHOS_C54170.html) |
| LED3 | LED Green | 5mm | - | [Hubei KENTO Elec <br> C54166](https://lcsc.com/product-detail/Light-Emitting-Diodes-LED_f5Short-legs-Round-with-edge-Pu-bright-transparent-green-green-Bagged-RHOS_C54166.html) |
| LED4 | LED Red (small) | 3mm | - | [Hubei KENTO Elec <br> 3AR4PD08](https://lcsc.com/product-detail/Light-Emitting-Diodes-LED_f3Long-legs-Round-with-edge-Red_C2155.html) |
| SW1, SW2, SW3 | Switch Tactile | - | - | [E-Switch <br> TL3300DF160Q](https://www.digikey.com/products/en?keywords=EG4906CT-ND) |
| SW4 | Slide Switch, DPDT, On/On, Non-Shorting (BBM) | 2.54mm | - | [C&K <br> OS202011MA0QN1](https://www.digikey.com/product-detail/en/c-k/OS202011MA0QN1/CKN9563-ND/1981434) |
| P1 (GPIO) | Female Header, Double Row, Isolation Height: 11.05mm | 2,54mm | 2x20P | [No Name (AliExpress)](https://www.aliexpress.com/item/5pcs-2-54-mm-0-10-Pitch-2x20-40-Position-Dual-Row-PCB-Female-Header-Through/32832362977.html)<br>OR<br>[BOOMELE (LCSC)](https://lcsc.com/product-detail/Female-Header_2-54mm-2-20P_C35165.html) |
| I2S (4 pins), VGA Power Select (3 pins) | Male Pin Header, Single Row | 2.54mm | - | [SULLINS <br> PRPC040SAAN-RC](https://www.digikey.com/products/en?keywords=S1011EC-40-ND) |
| P3 | Connector for External Buttons | XH2.54 | 5P | [No Name (AliExpress)](https://www.aliexpress.com/item/10pcs-lot-20cm-XH-red-white-ribbon-cable-dual-head-same-direction-XH2-54-2P-3P/32816833194.html)<br>OR<br>[BOOMELE (LCSC)](https://lcsc.com/product-detail/XH-Connectors_XH-5A-5P-pitch2-5mm-Straight-line_C2318.html) |
| P4 | Connector for External LEDs | XH2.54 | 7P | [No Name (AliExpress)](https://www.aliexpress.com/item/10pcs-lot-20cm-XH-red-white-ribbon-cable-dual-head-same-direction-XH2-54-2P-3P/32816833194.html)<br>OR<br>[BOOMELE (LCSC)](https://lcsc.com/product-detail/XH-Connectors_XH-7A-7P-pitch2-5mm-Straight-line_C10384.html) |
| P# (FAN) | Connector for Fan | XH2.54 | 2P | [No Name (AliExpress)](https://www.aliexpress.com/item/10pcs-lot-20cm-XH-red-white-ribbon-cable-dual-head-same-direction-XH2-54-2P-3P/32816833194.html)<br>OR<br>[Ckmtw (LCSC)](https://lcsc.com/product-detail/XH-Connectors_2501series-socket-1-2P-2-54mm-Curved-needle_C132478.html) |
| P2, P5, P6 (DNI) | - | - | - | - |
| P7 (pins 1,2,4-8) P9 (1 pin) | Long Male Header | 2.54mm | 40 Pin (cut) | [C51353 <br> (Boom Preceision ELEC)](https://lcsc.com/product-detail/_Boom-Precision-Elec-Headers-Pins-pitch2-54mm-length21mm_C51353.html) |
| Q1 | Transistor NPN | SOT23 | BC847 | [ON <br> BC847BLT1G](https://www.digikey.com/products/en?keywords=BC847BLT1GOSCT-ND) |
| J1 | VGA Connector, 15 Pos, 3 Row, Female Connector, Right Angle | D-Sub | - | [Omron <br> XM4L-1542-132](https://www.digikey.com/product-detail/en/omron-electronics-inc-emc-div/XM4L-1542-132/OR1096-ND/1829580) |
| J2 | Phone Jack 3.5mm, Right Angle | - | - | [CUI <br> SJ1-3523N](https://www.digikey.com/products/en?keywords=CP1-3523N-ND) |
| J3 | Micro SD-Card Holder | - | - | [No Name (AliExpress)](https://www.aliexpress.com/item/10pcs-lot-9pin-Micro-SD-card-slot-connectors-size-14-15mm-TF-card-deck-fit-for/32763208642.html?spm=a2g0x.10010108.1000016.1.76105513wSfAxQ&isOrigTitle=true)<br>OR<br>[SOFNG (LCSC)](https://lcsc.com/product-detail/Card-Sockets_TF-015_C113206.html)|
| J4 | USB 3.0, Female, Right Angle | Type A | 9 pins | [Jing <br> C69073](https://lcsc.com/product-detail/USB-Connectors_Jing-Extension-of-the-Electronic-Co-LCSC-A-F-90degree-3-0Outside-the-buckle-copper-shell-curling-has-curled-Not-high-temperature_C69073.html) |
| FAN | Fan | 40x40x10 | 5V |  [Sunon <br> MF40100V2-1000U-A99](https://www.digikey.com/products/en?keywords=259-1795-ND) (Very Noisy)<br>or<br>[Noctua NF-A4x10 5V](https://noctua.at/en/products/fan/nf-a4x10-5v) (quiet, costly) |
| JMPR | Jumper for Pin-Header | 2.54mm | 2 Pin |  [Sullins <br> SPC02SYAN](https://www.digikey.com/products/en?keywords=S9001-ND) |
| HEATSINK | Heatsink | 21x21x11.5 | - | [Wakefield-Vette <br> 624-45ABT3](https://www.digikey.com/products/en?keywords=345-1089-ND) |

### Example of 5.2 BOM on Octopart:
https://octopart.com/bom-tool/KurIZPWc

## Convenient order of manual soldering:
1) resistors, capacitors, diodes, transistor
2) SD socket
3) buttons
4) LEDs
5) connectors, jumpers, switch

## P7, P9 Notes
1) Cut connector to 8 pins
2) Remove 3rd pin (use for P9)
3) Insert pins through IO board into DE10-Nano
4) Solder from top
5) Trim pins flush


