# ATmega644P/1284P core for Arduino IDE 1.6.7

This core adds full support for ATmega644P and ATmeg1284P microcontrollers
into the Arduino IDE.

## WARNING! This version only works with IDE >= 1.6.7.


### Installation

1) Close the IDE and, if you manually installed it in the past, remove the 
old core from your_sketchbook_folder/hardware

2) Restart the IDE, then select "File/Preferences" from the menu

3) Go to “Additonal Boards Manager URLs” and press the icon to the right
of the text area, then insert the following line into the pop-up window:
http://www.leonardomiliani.com/repository/package_leonardomiliani.com_index.json

4) Click OK twice, then go to “Tools/Board/Boards Manager”. Wait for a
couple of seconds for the boards manager to refresh the list of the additional
boards, then scroll the list until you find the following entries:
- Atmega168P/328P Boards by Leonardo Miliani version x.x.x
- Atmega644P/1284P Boards by Leonardo Miliani version x.x.x
- ATtiny extra board by Leonardo Miliani version x.x.x

5) Just select the core you want to install then press the corresponding
“Install” button. At the end of the installation the core will be set and
ready and the new boards will be available from “Tools/Board” without
the need to restart the IDE. Enjoy!

6) If you prefer to manually install the library (you'll loose the ability to automatically
update the software) you can download the ZIP and add it to your collection of libraries
just by installing it from "Sketch/Library inclusion/Library manager" and then choosing the ZIP file.


### Hints and Tricks

To set up an MCU to a specific clock, the first thing to do is writing the bootloader, even you won’t use it in the future.
This must be done because the IDE changes the fuse in the proper manner to set up the microcontroller to work with the correct
clock source (for 1 & 8 MHz, the internal oscillator will be used, for 16 MHz an external crystal will be used).
To do this, choose the proper board from “Tools/Micro” in the menu, then choose “Tools/Burn bootloader”. If you want to upload
your sketches using the bootloader you have to choose “Atmega644P @ 16 MHz w/Optiboot” or “Atmega1284P @ 16 MHz w/Optiboot” because
the bootloaders that come with this pack are compiled to work at 16 MHz only.

After this, you can choose to upload your sketches using the bootloader or via ISP programming. In the first case, connect
the pin RX/TX of the microcontroller to your USB/Serial converter, then upload your sketches by choosing “File/Upload” from the menu or
by clicking on the upload icon.
In the latter case, connect the MOSI/MISO/SCK/RESET pins of the microcontroller to the corresponding pins of the programmer you are
using, then upload your sketches by choosing “File/Upload with a programmer” from a menu.


### Issues when uploading a sketch using the bootloader

Some people reported problems when tried to upload a sketch using the Optiboot bootloader, mostly
using ATmega1284P.

A lot of speculations has been written about this issue. Someone said that it could be a problem
related to the use of incorrect fuses, other said that it was an hardware issue.

I used a set of fuses that in almost all the cases seem to not manifest the issue. A very few
cases has been reported where the upload didn’t work. In these last cases I suggest to set an
RC filter on pin RX using a 10K resistor in series to the RX line and a 100nF capacitor pulled
to ground. Put the filter as close as possible to the RX pin of the ATmega644P/1284P and try
again. Refer to the schematic to set up a standalone 1284P with the RC filter:

TX)------------- // -------- (RX
RX)--+-[R 10K]-- // -------- (TX
     |
   C 100n
     |
     |
    ___
     _
     

For more informations on cores, libraries and other stuff for Arduino and Atmel
microcontrollers, see my website at: http://www.leonardomiliani.com
or my GitHub repos at: https://github.com/leomil72

### Supported MCUs:

This core supports ATmega644P/PA and ATmega1284P.
You could use ATmega644 and ATmega1284 too, but:
1) you should add the entries into the file boards.txt by yourself;
2) you could modify the Arduino core to set up the support for the “non-P” MCUs;
2) you would go to use old cores that don’t have the new power saving technologies introduces by PicoPower cores in “P“ & “PA“ series.


### Credits & warranty

This is core is: 
- based on core Mighty-1284p by maniacbug
- based on Optiboot 4.5 by westfm

The core is released in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even
the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.


### License

Released under the terms of the GNU Lesser General Public License version 2.1 (LGPLv2.1)

Work based on Sanguino and mighty-1284 cores, on Optiboot from westfm and other.