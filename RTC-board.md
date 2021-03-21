
![photo](pictures/rtc.jpg)

Some cores (ao486, Minimig) use clock, so MiSTer provides the real time for such cores. MiSTer can take the time from internet if active connection is present. 

This board is pretty simple and provide real time offline. It supports 2 types of battery holders and several types of RTC ICs. It's plugged into LTC connector.

![photo](pictures/rtc_inside.jpg)

## Assembling notes
* If through hole battery holder is used, you need to cut all its plastic pins and make sure the holder is fully seated on board without gaps. Otherwise it may touch the I/O board and make short circuit.
* For through hole holder, make sure you cut the pins as short as possible so it won't protrude under the board which can make short circuit.
* The board has the hole on opposite side of connector. Use a plastic(or other non-conductive) screw to make a leg and prevent the board bend and touch the main board.
* SMD holder (left picture) is preferable as it's more slim.

## Usage notes
To get real time saved, simply connect MiSTer to internet and let it run for around 15 minutes.
or from the console: 

By default the time zone is UTC(GMT). If you want to get the time of your zone, you need to do following:
* connect to MiSTer by FTP/SFTP
* navigate to /usr/share/zoneinfo/posix folder and find there the name of your place or time zone.
* copy that file to your computer under name timezone
* copy it back to MiSTer to folder /media/fat/linux with name timezone

From the console you can also force the hardware clock to update and read the time from it.
* _store datetime to RTC_ : **hwclock -wu**
* _read RTC_ : **hwclock -u**