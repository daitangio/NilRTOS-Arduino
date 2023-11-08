# Introduction
This is a fork of [Greiman NilRTOS](https://github.com/greiman/NilRTOS-Arduino), tiny RTOS library for AVR Arduino boards.

The aim of the fork is to simplify further Nil, reducing it to the essential part to ease learning how it works.

# Getting started



# History
The base code for NilRTOS was written by Giovanni Di Sirio, the author
of ChibiOS/RT.

http://www.chibios.org/dokuwiki/doku.php

To install NilRTOS, copy the NilAnalog, NilRTOS, NilTimer1, and
TwiMaster folders to your Arduino/libraries folder.

The data logger examples requires a version of the SdFat
library that is newer than 20130701.  A newer version of SdFat is 
included in the libraries folder.  The latest versuin of SdFat is at:

https://github.com/greiman/SdFat

SD logger examples require a quality SD card to avoid overruns.
Adjust the number of ADC channels and the interval between data
points to match the capabilities of your SD card.

Please read NilRTOS.html for more information.

diff_ru.txt is a diff of the original files with the library version.