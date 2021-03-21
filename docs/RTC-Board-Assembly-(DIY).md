## NOTE
This page is for reference only. It may not be up to date. It may not include the BOM for latest PCB version. You need to check the schematic and required components yourself!


The following section will walk you through the steps of creating your own Mister RTC Board. It describes where to order all necessary parts like PCB and components. It will also give you an overview on the equipment you need and show you how to assemble the board.


![picture](pictures/RTC_Board_DIY.png)

------

### 1. Order PCB

#### Approved PCB Manufactors
  * [PCBway](https://www.pcbway.com/setinvite.aspx?inviteid=43024) - [Quick order RTC v1.2](https://www.pcbway.com/project/shareproject/RTC_for_MiSTer_v1_2.html) - [Quick order RTC v1.3 (with temp sensor)](https://www.pcbway.com/project/shareproject/W43024ASU40_rtc_1_3.html)
  * [EasyEDA](https://easyeda.com/)
  * [JLCPCB](https://jlcpcb.com/)
  * [OSH Park](https://oshpark.com/)

#### PCB Layout (Gerber Files)
Check the MiSTer hardware repository for the most recent PCB files: [MiSTer_Hardware](https://github.com/MiSTer-devel/Hardware_MiSTer)


------

### 2. Order Components

This is a general overview of the components, including reference parts that were successfully used to assemble a MiSTer RTC Board <b>version 1.2</b>.

#### General Components:
The components in this table are the general components. You will have to choose additionally a RTC chip and crystal combination from the next table

| Name | Component | Package | Value | Reference Parts |
|---|---|:---:|:---:|---|
| C1 | Capacitor (Ceramic) | 0805 | 10uF | [KEMET <br> C0805C106K8PACTU](https://www.digikey.com/products/en?keywords=399-4925-1-ND) |
| R1, R2 | Resistor 1% 1/8W | 0805 | 4.7K | [Yageo <br> RC0805FR-074K7L](https://www.digikey.com/products/en?keywords=311-4.70KCRCT-ND) |
| B1 | Coin Cell Holder for CR1220 | 12mm | - | [MPD <br> BK-885](https://www.digikey.com/products/en?keywords=BK-885-ND) |
| P1 | GPIO Connector | 2mm | 18 Pin | [Amphenol <br> 63453-118LF](https://www.digikey.com/products/en?keywords=%09609-2663-ND) |

#### RTC / Crystal Table
The RTC Chip (U1) / Crystal (X1) combination in this table are approved by users that successfully build a RTC Board version 1.2

| Name | Component | Package | Value | Reference Parts |
|---|---|:---:|:---:|---|
| U1 | I2C RTC Chip: <br> M41T81 | 8-SOIC | - | [ST <br> M41T81M6F](https://www.digikey.com/products/en?keywords=497-4709-1-ND) |
| X1 | Crystal: <br> 32.768kHz ±20ppm, 12.5pF, 50 kOhms  | Cylindrical Can | - | [Citizen <br> CMR200T32768DZFT](https://www.digikey.com/products/en?keywords=%09300-8340-6-ND)|

### Example of BOM on Octopart
https://octopart.com/bom-tool/95qomeBj