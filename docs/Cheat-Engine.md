# Setup

Cheats should be stored in:  `cheats/system/rom_filename.zip` where system is name of the core like NES, SNES, Genesis, etc..

So, for example: 
`cheats/NES/Taboo (USA).zip` for the NES ROM `Taboo (USA).nes`

The filename of the zip must match the ROM name exactly. Cheats will be loaded automatically when you load a ROM, and can be enabled and disabled from the menu in supported cores.

If the .zip cheat file does not match the ROM name, the cheat engine will automatically check the ROM CRC32 and select the appropriate .zip cheat file with matching CRC32 accordingly. ROM name matching has priority over CRC32 checking.

Individual cheats are in .gg format and should be stored in zip files. Packs of codes can be downloaded from https://gamehacking.org/ by selecting the MiSTer format and choosing to save all codes for a given game.



# Making your own codes

All types of cheat codes for 16 bit systems and earlier can be decoded into four pieces of information: An address, a compare value, a replace value, and usually a flag to say if the compare value is used or not. The format for a gg file is in binary as 4 32 bit integers in little-endian byte order. 

For example, if the Address is `0xFF1CA0` and the compare value is `0xB5` and the replace value is `0xFF`, the file would look like this:

`01 00 00 00  A0 1C FF 00  B5 00 00 00  FF 00 00 00`

The first four bytes are little-endian `0x00000001` for "compare enabled", the second four are little-endian address, third set are compare value, and fourth is replace value. Note that not all codes use a compare value.

For cheats with multiple codes, simply add another 16 bytes at the end of the file in the same format as the first.

You can decode game genie codes into these values with tools like this:
https://gamehacking.org/system/nes
