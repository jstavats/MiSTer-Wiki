## Requirements
In order to get started with the MiSTer platform, there are a few things that will be required. Optional [addons](https://github.com/Hackshed/MiSTerDocumentation/wiki/How-to-get-your-own-addon-boards) are also available but for the bare minimum setup, you will need the following items:

* [DE10-Nano Board](How-to-start-with-MiSTer#1-de10-nano-board) with supplied power supply and SD card. (required)
* [USB OTG connector or OTG USB hub](How-to-start-with-MiSTer#2-usb-connection)(required)
* USB Keyboard (required)
* HDMI Monitor & HDMI Cable (required)
* [Cooling](How-to-start-with-MiSTer#3-cooling-fpga) (recommended)
* Network Connection (recommended for initial setup and updates) 
* Micro SD card reader (required for initial setup)
* [Upgraded power supply](https://github.com/MiSTer-devel/Main_MiSTer/wiki/How-to-start-with-MiSTer#4-upgraded-power-supply-recommended) (recommended for users using the usb hub and lots of power hungry devices)

## 1. DE10-Nano board
The heart and engine of the whole platform is the **Terasic DE10-Nano** development board, made in Taiwan.

You can buy it:
* Directly from [Terasic Inc.](http://www.terasic.com.tw/cgi-bin/page/archive.pl?Language=English&No=1046&PartNo=8)

Or from major electronics suppliers such as:
* [Mouser](http://www.mouser.com/ProductDetail/Terasic-Technologies/P0496/)
* [Digikey](https://www.digikey.com/product-detail/en/terasic-inc/P0496/P0496-ND/6817231)

A power supply unit (PSU) and 8GB MicroSD card is included with the kit. The SD card can be reformatted to use with your MiSTer.
Any MicroSD card 2GB and larger should work fine as well. Speed class doesn't affect it.

## 2. USB connection
Most unpowered basic USB hubs will work. Although it is recommended that you use a powered USB OTG hub with your DE10-Nano board as it is not able to handle high current consumption, so depending on the peripherals you use, you may need an external powered hub. 

If you're not connecting too many USB peripherals, it does handle a keyboard, mouse, and gamepad just fine. Do note that the USB socket isn't very robust so it is best to avoid connecting and disconnecting too often. 

### USB option 1:
**Micro USB OTG cable + basic USB 2.0 hub.** 

A basic USB 2.0 hub, or one with external power would be a good idea both to eliminate OTG socket reliability issues and provide power to external devices. Some cheap ones on eBay/Aliexpress may be declared as full speed USB 2.0 but in fact work in USB low speed mode. They may be acceptable for keyboard, but better to avoid them.

### USB option 2:
**USB OTG Hub.** 

These hubs are designed to connect directly to the micro-USB OTG port and require less inter-connection cables. Such hubs are also available on eBay/Aliexpress.

### USB option 3:
**[USB hub daughter board.](https://github.com/MiSTer-devel/Main_MiSTer/wiki/USB-Hub-daughter-board)** 

You can assemble or purchase this board that provides 7 USB ports available to the MiSTer system.

## 3. Cooling

The hybrid ARM+FPGA chip has been found to get hot even when idling in the core menu, therefore some passive cooling is recommended. The main heat producer in the chip is the integrated dual-core ARM processor producing a constant heat regardless of the FPGA core in use. 

The Cyclone V FPGA chip on the DE10-Nano board is industrial grade and supports up to 100°C, but for guaranteed long term usage without degrading its characteristics,  it's highly advisable to add at least a heatsink. 

This chip is approximately 21.5mm x 21.5mm. Ideal dimensions of a heatsink is 22mm x 22mm, and it will cover all the FPGA. Commonly found heatsinks with dimensions ranging from 20mm x 20mm to 25mm x 25mm can be used,  but for larger heatsinks pay attention to nearby components, they must not touch the heatsink. 

The height of the heatsink should be no more than 10mm if an I/O board is used because it could touch parts in the I/O board and create short circuits.

### Active cooling 

Some large cores such as ao486 and Minimig are sensitive to FPGA chip temperature and become unstable if it becomes too hot. So active cooling, in addition to passive cooling, is recommended for stability. 

If you're building or purchasing an [I/O board](https://github.com/MiSTer-devel/Main_MiSTer/wiki/IO-Board), they are designed for a 40mm x 40mm fan. Assembled I/O boards should already have a fan installed. 

If you do not use any I/O boards then you are free to choose any fan, but bear in mind that you should only use the 5V line from the Terasic DE10-Nano board to drive a 5V fan. (The DE10-Nano's 9V line is deliberately hidden by the MiSTer I/O board to prevent any possibility of accidentally shorting it to any other signals.) You may also consider a larger 12V fan, they should work but spin slower and still provide good airflow. (Do note that popular Noctua fans may not spin up when undervolted). 

A large selection of fans can be found on most electronic components sites, such as [Digikey](https://www.digikey.co.uk/products/en/fans-thermal-management/dc-fans/217?FV=38007c%2Cffe000d9%2Cb89e93&quantity=0&ColumnSort=0&page=1&pageSize=25&pkeyword=40mm+fan), Mouser and many others.

## 4. Upgraded Power Supply (recommended)

If you are going to use the official USB Hub add-on board with many peripherals attached, then there will be a much larger current draw required of the stock PSU than it was originally designed for. This could lead to instability and should be avoided. If you are using a usb hub add-on board, you should upgrade to a 4amp or greater power supply to provide sufficient current to both. When replacing the power supply make sure to get one that is relatively high quality, as the DE10-Nano could become damaged if you switch to a cheap badly-made power supply. Here's a Mean Well Power Supply Unit that is highly recommended:

Amazon: https://www.amazon.com/gp/product/B01D0Z8PLW/  
Digikey: https://www.digikey.com/short/43cbh4  
Mouser: https://www.mouser.com/ProductDetail/MEAN-WELL/GST25A05-P1J/?qs=drgMNd%252BkGPOX8brSXUPVtQ%3D%3D

This power supply would also require the appropriate female IEC 320 C13 power cable for your outlet that is appropriate for your region.