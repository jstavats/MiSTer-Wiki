This is a small add-on board giving ability to use external audio device as a tape input
![picture](pictures/ADCin_1.jpg)


![picture](pictures/ADCin_2.jpg)

**Warning: there is a capacitor (C12) on I/O board close to ADC-in board. Make sure you don't short it!**


![picture](pictures/ADCin_3.jpg)

Note: a spacer board added to fit the ADC-in board tight in place, so it won't popup.

ADC chip used on DE10-nano is connected that way so it accepts only positive voltage. It means it's not suitable for quality audio as negative wave won't be processed. But it's enough to be used as tape input. For good quality audio input it requires more complex circuit with adding the offset. 

Current ADC-in board provides stereo input. It also can be used for other analog signals with up to 250KHz and up to 2.5V.

[Order ADC-in board PCB on PCBWay](https://www.pcbway.com/project/shareproject/ADC_in_board_for_MiSTer_v1_1.html)

[Order ADC-in spacer board PCB on PCBWay](https://www.pcbway.com/project/shareproject/ADC_in_spacer_board_v1_1.html)
