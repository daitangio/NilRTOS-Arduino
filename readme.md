# Introduction
This is a fork of [Greiman NilRTOS](https://github.com/greiman/NilRTOS-Arduino), tiny RTOS library for AVR Arduino boards.

The base code for NilRTOS was written by Giovanni Di Sirio, the author of ChibiOS/RT: http://www.chibios.org/dokuwiki/doku.php


__The aim of the fork is to simplify further Nil, reducing it to the essential part to ease learning and increase interoperability with other libraries__


# Getting started using vscode and ArduinoMakefile

To better study NilRTOS, we suggest to use VSCode with C/C++ integration or GNU Emacs.


- A Linux / macOS environment is easier to setup, because we use command line build (ArduinoMakefile project) during development.
- Install Arduino Legacy 1.8.13 IDE from https://www.arduino.cc/en/software
- Ensure you have gnu make installed
- Ensure you have doxygen tool installed if you want to generate the reference documentation (doxygen was used by Giovanni Di Sirio and was mantained to provide better documentation).

# TO DO LIST

- [x] Fork project
- [ ] DOCUMENT asm usage
- [ ] Remove unused code
- [ ] Fine tune doxygen




# Getting started using Arduino IDE 1.8.x (discouraged approach)
To install NilRTOS, copy the NilAnalog, NilRTOS, NilTimer1, and
TwiMaster folders to your Arduino/libraries folder.

The data logger examples requires a version of the SdFat
library that is newer than 20130701.  A newer version of SdFat is 
included in the libraries folder.  The latest version of SdFat is at:

https://github.com/greiman/SdFat

SD logger examples require a quality SD card to avoid overruns.
Adjust the number of ADC channels and the interval between data
points to match the capabilities of your SD card.

Please read NilRTOS.html for more information.

diff_ru.txt is a diff of the original files with the library version.