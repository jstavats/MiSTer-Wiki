## NOTE
This page is for reference only. It may not be up to date. It may not include the BOM for latest PCB version. You need to check the schematic and required components yourself!


The following section will walk you through all steps of creating your own SDRAM Board. It describes where to order all necessary parts like PCB and components. It will also give you an overview on the equipment you need and show you how to assemble the board.

### Universal board:
![picture](pictures/SDRAM_Board_DIY.png)

### Extra slim board:
![picture](pictures/SDRAM_XS_Board_DIY.png)

------

### 1. Order PCB

#### Approved PCB Manufactors
* [PCBway](https://www.pcbway.com/setinvite.aspx?inviteid=43024)
* [EasyEDA](https://easyeda.com/)
* [JLCPCB](https://jlcpcb.com/)
* [OSH Park](https://oshpark.com/)

#### PCB Layout (Gerber Files)
Check the MiSTer hardware repository for the most recent PCB files: [MiSTer_Hardware](https://github.com/MiSTer-devel/Hardware_MiSTer)

* [Extra slim SDRAM Board v2.2 (single chip)](https://github.com/MiSTer-devel/Hardware_MiSTer/raw/master/releases/sdram_xs_2.2.zip) --> [One-Click Order (PCBWay)](https://www.pcbway.com/project/shareproject/SDRAM_XS_board_for_MiSTer_v2_2.html)

* [Extra slim SDRAM Board v2.4 (dual chip)](https://github.com/MiSTer-devel/Hardware_MiSTer/raw/master/releases/sdram_xsd_2.4.zip) --> [One-Click Order (PCBWay)](https://www.pcbway.com/project/shareproject/SDRAM_XSD_board_for_MiSTer_v2_4.html)

* [Universal SDRAM Board v3.1U](https://github.com/MiSTer-devel/Hardware_MiSTer/raw/master/releases/sdram_uni_3.1U.zip) --> [One-Click Order (PCBWay)](https://www.pcbway.com/project/shareproject/MiSTer_SDRAM_board_v3_1__Universal_.html) (obsolete)


------

### 2. Order Components
This is a general overview of the components, including reference parts that were successfully used to assemble a MiSTer SDRAM Board.

#### SDRAM Board v2.4/v2.5 (dual chip)

top row: 10uf, 0.1uf, 10uf, 0.1uf<br> 
bottom row: 10uf, 1uf, 1uf, 10uf, 10uf, 1uf, 1uf, 10uf<br> 

| Name | Component | Package | Value | Reference Parts |
|---|---|:---:|:---:|:---:|
| - | Capacitor (Ceramic) | 0805 | 0.1uF | [KEMET <br> C0805C104J5RACTU](https://www.mouser.com/ProductDetail/KEMET/C0805C104J5RACTU?qs=sGAEpiMZZMs0AnBnWHyRQFCCI5cSbRT%2FIwsdZoDYv9I%3D) |
| - | Capacitor (Ceramic) | 0805 | 1uF | [KEMET <br> C0805C105K4RAC7210](https://www.mouser.com/ProductDetail/KEMET/C0805C105K4RAC7210?qs=sGAEpiMZZMt7gvpyg0xT8tkC78e7yyZ9nXXQ3YPCDvc=) |
| - | Capacitor (Ceramic) | 0805 | 10uF | [KEMET <br> 1C0805C106J8RACAUTO](https://www.mouser.com/ProductDetail/KEMET/C0805C106J8RACAUTO?qs=sGAEpiMZZMs0AnBnWHyRQN7%2FAA2D2lPPgWq9qdkMgizvU7%252BgdNn0uA%3D%3D) |
| U1/2 | DRAM 512MBIT | TSOP-54 | 64 MB | [Alliance Memory <br> AS4C32M16SB-6TIN ](https://www.mouser.com/ProductDetail/913-AS4C32M16SB-6TIN) or [AS4C32M16SB-7TIN ](https://www.mouser.com/ProductDetail/Alliance-Memory/AS4C32M16SB-7TIN?qs=sGAEpiMZZMti5BT4iPSEnReBopsBxV3sVReadJBJNZQ%3D)|
| U3 | Inverter | SOT-23-5 | - | [Texas Instruments <br> SN74LVC1G04DBVR](https://www.mouser.com/ProductDetail/Texas-Instruments/SN74LVC1G04DBVR?qs=sGAEpiMZZMutVWjHE%2FYQw%252B6L8ySpGowMh2os9RClt54%3D) |
| P1 | 2x20 (40 Pos.) Female Header, Double Row, Right Angle | 2,54mm Pitch | - | [No Name (AliExpress)](https://www.aliexpress.com/item/20Pcs-Per-Lot-2-54mm-Pitch-2x20-Pin-40-Pin-Female-Double-Row-Right-Angle-Pin/32758316130.html) |

#### Extra slim v2.2 board (SDRAM XS v2.2)

| Name | Component | Package | Value | Reference Parts |
|---|---|:---:|:---:|:---:|
| C1 - C7 | Capacitor (Ceramic) | 0805 | 0.1uF | [KEMET <br> C0805C104J5RACTU](https://www.digikey.com/products/en?keywords=399-1171-1-ND) |
| U1 | IC SDRAM 256MBIT 166MHZ 32MB | TSOP-54 | 32 MB | [Alliance Memory <br> AS4C16M16SA-6TCN](https://www.digikey.com/products/en?keywords=1450-1252-ND) or [Winbond W9825G6KH-6](https://lcsc.com/product-detail/DDR_Winbond-Elec-W9825G6KH-6_C62246.html) |
| P1 | 2x20 (40 Pos.) Female Header, Double Row, Right Angle | 2,54mm Pitch | - | [No Name (AliExpress)](https://www.aliexpress.com/item/20Pcs-Per-Lot-2-54mm-Pitch-2x20-Pin-40-Pin-Female-Double-Row-Right-Angle-Pin/32758316130.html) |


#### Universal v3.1U vertical board (obsolete)

| Name | Component | Package | Value | Reference Parts |
|---|---|:---:|:---:|:---:|
| C1 - C5 | Capacitor (Ceramic) | 0805 | 0.1uF | [KEMET <br> C0805C104J5RACTU](https://www.digikey.com/products/en?keywords=399-1171-1-ND) |
| U1 | IC SDRAM 256MBIT 166MHZ 32MB | TSOP-54 | 32 MB | [Alliance Memory <br> AS4C16M16SA-6TCN](https://www.digikey.com/product-detail/en/alliance-memory-inc/AS4C16M16SA-6TCN/1450-1252-ND/5214128) or Winbond W9825G6KH-6 |
| P1 | 2x20 (40 Pos.) Female Header, Double Row, Right Angle | 2,54mm Pitch | - | [No Name (AliExpress)](https://www.aliexpress.com/item/20Pcs-Per-Lot-2-54mm-Pitch-2x20-Pin-40-Pin-Female-Double-Row-Right-Angle-Pin/32758316130.html) |
| P2 | 1x3 (3 Pos.) Male Pin Header, Single Row, Right Angle, <br> Contact Length: 5.84mm (Mating), 5.84mm (Post), Insulation Height: 2.54mm | 2,54mm Pitch | - | [Sullins Connector <br> PRPC040SBBN-M71RC](https://www.digikey.com/products/en?keywords=S1121EC-40-ND) |


#### Universal v3.1U horizontal board (obsolete)

| Name | Component | Package | Value | Reference Parts |
|---|---|:---:|:---:|:---:|
| C1 - C5 | Capacitor (Ceramic) | 0805 | 0.1uF | [KEMET <br> C0805C104J5RACTU](https://www.digikey.com/products/en?keywords=399-1171-1-ND) |
| U1 | IC SDRAM 256MBIT 166MHZ 32MB | TSOP-54 | 32 MB | [Alliance Memory <br> AS4C16M16SA-6TCN](https://www.digikey.com/products/en?keywords=1450-1252-ND) or Winbond W9825G6KH-6 |
| P1 | 2x20 (40 Pos.) Female Header, Double Row, Isolation Height: 11mm | 2.54mm | - | [No Name (AliExpress)](https://www.aliexpress.com/item/10-Pcs-2-54mm-Pitch-2x20-Pin-40-Pin-Female-Double-Row-Long-Pin-Header-Strip/32791223993.html) |
| P2 | 1x3 (3 Pos.) Male Pin Header, Single Row, Straight, <br> Contact Length: 6.1mm (Mating), 3mm (Post), Insulation Height: 2.54mm | 2.54mm | - | [Sullins Connector <br> PRPC040SAAN-RC](https://www.digikey.com/products/en?keywords=S1011EC-40-ND) |

#### Bill of Material
User approved BOMs and One-Click shopping Carts. If you have successfully build a MiSTer IO Board and used your own components, then share them with us :)
* [Octopart: SDRAM Board (3.1U, Vertical)](https://octopart.com/bom-tool/7Rk7V11w) (Missing Parts: P1)
* [Octopart: SDRAM Board (3.1U, Horizontal)](https://octopart.com/bom-tool/x1qGHooE) (Missing Parts: P1)
* For extra slim board 1.1 use BOM for vertical v3.1U, just add one more capacitor.

------

### 3. Assemble the Board

#### Soldering Tutorial
[SDRAM Board v3.1](https://www.youtube.com/watch?v=bq04AH7tiV0) (by [Negative Solution](https://www.youtube.com/channel/UCLHmCwunWQkMvrlgE2BJXTw)):

<a href="https://www.youtube.com/watch?v=bq04AH7tiV0" target="_blank">
  <img src="http://img.youtube.com/vi/bq04AH7tiV0/0.jpg" alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>

### Extra slim board notes:
Soldering this board is a little tricky. The board has SDRAM chip laid over connector, so connector should be soldered with neither pins nor solder protruding the board. See the picture:
![picture](pictures/SDRAM_XS_semi.jpg)
How to cut the pins at the same level and prevent them protruding without special equipment? Insert the connector and using sharp flat nippers trim the pins as close to board as possible. Take the standard printer paper and bend it once, so you will get the 2 layers of paper. Insert these 2 layers of paper between the board and connector. Pins of connector will sink to the level (or slightly dipper) of traces. Solder the pins. Remove the paper. Use solder wick to remove the excessive amount of solder, but make sure it's enough solder remains inside the holes, so pins won't be disconnected with mechanical force. Solder the SDRAM chip and other components.