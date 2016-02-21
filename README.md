# ATmega644/644P/1284P core for Arduino IDE 1.6.7

This core adds full support for ATmega644/644P and ATmeg1284P microcontrollers
into the Arduino IDE.

WARNIGN! This version only works with IDE >= 1.6.7.


* Installation

1) Close the IDE and, if manually installed in the past, remove the
old cores from your_sketchbook_folder/hardware

2) Restart the IDE, then select "File/Preferences" from the menu

3) Go to “Additonal Boards Manager URLs” and press the icon to the right
of the text area, then insert the following line into the pop-up window:
http://www.leonardomiliani.com/repository/package_leonardomiliani.com_index.json

4) Click OK twice, then go to “Tools/Board/Boards Manager”. Wait for a
couple of seconds for the boards manager to refresh the list of the additional
boards, then scroll the list until you find the following entries:
- Atmega168P/328P Boards by Leonardo Miliani version x.x.x
- Atmega644/644P/1284P Boards by Leonardo Miliani version x.x.x
- ATtiny extra board by Leonardo Miliani version x.x.x

5) Just select the core you want to install then press the corresponding
“Install” button. At the end of the installation the core will be set and
ready and the new boards will be available from “Tools/Board” without
the need to restart the IDE. Enjoy!
