---
layout: page
title: LibrePager
description: A modern pager that belongs to nobody but you.
background: '/img/IMG_1511.JPG'

---


# Touchscreen Testbed

The Touchscreen Testbed (TS_testbed) is a soldered breadboard designed to connect commercially available touchscreen dev boards to the target mcu dev board, the ESP32 Devkit V1 to test software. 

<img src="/img/IMG_1531-500-100-populated board .png" width="90%" ><br>
This is the Touchscreen Testbed populated with a ILI9341 resistive touchscreen and a ESP32 Devkit V1 (30 pin) dev board, ready to plug into your computer with a usb cable to download code and/or to power for testing. Notice the 2x5 pin block below the dev board for connection to Espressif's JTAG hardware debugging board, the [Esp_Prog](https://docs.espressif.com/projects/espressif-esp-iot-solution/en/latest/hw-reference/ESP-Prog_guide.html).<br>


<img src="/img/IMG_1533-500-100 bare board.jpg" width="90%" ><br> 
Here's the same soldered breadboard with the touchscreen and dev board removed.<br>
<img src="/img/TS_Tb_fritzing.png" width="90%" ><br>
And this is the wiring diagram for the same device.


# How we designed it. 

The easiest way to explain it is to send you to the excellent [XTronical tutorial for ILI9341 resistive touchscreen](https://www.XTronical.com/esp32ili9341).  Here's another link to the [YouTube video](https://www.youtube.com/watch?v=rq5yPJbX_uk) demonstrating XTronical's finished device. 

In a straight forward way, the Touchscreen Testbed uses SPI drivers from the [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI) library by Bodmer to drive compatible touchscreens. 



Here is a link to our LibrePager  [ESP32_Graphic_Testbed](https://github.com/librepager/ESP32_Graphic_Testbed) Code Repository.  This code was generated using Visual Code Studio with PlatformIO, to load test device. 
* Notice how in /scr/main.cpp there are many different ways that we tried out the functions of the TFT_eSPI library and commented out the lines. 
* Much of the magic of the TFT_eSPI library is controlled by selections made in the /lib/TFT_eSPI/User_Setup.h file. You must make custom changes in this file to select the correct touchscreen driver chip and to select the functions of the pins for the SPI buss.  
* We used the XTronical wiring recommendations with one exception:
we used pin 5 instead of pin 15 for TFT_CS.  This change allowed us to exposes the pins for connection to Espressif's JTAG hardware debugging board, the [Esp_Prog](https://docs.espressif.com/projects/espressif-esp-iot-solution/en/latest/hw-reference/ESP-Prog_guide.html), which uses pin 15. 
* We had limited success coding for the touchscreen devices until we built these circuits in a soldered breadboard. We tried it using solderless breadboards, but intermittent open circuit problems confused debugging substantially. 
