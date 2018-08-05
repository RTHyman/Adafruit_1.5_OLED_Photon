# Adafruit_1.5_OLED_Photon

## Overview 

This is a repo to test functionality of Adafruit 1.5 inch OLED SPI connection to Particle.io and provide comprehensive instructions. 

**First step is wiring:**

Connect an Adafruit SSD1351 1.5" Color OLED breakout board to a Particle Photon. 

**Second step is to setup and run code:**

This guide is designed to help new users use the Particle IDE to run testing for the Adafruit 1.5 inch OLED. Next step is to make this guide functional by downloading the repo to local desktop and then use Particle CLI to compile and run.

## Wiring

**Limitations**

MicroSD Card is not currently supported
Should be possible, but I haven't yet gotten it working. See https://community.particle.io/t/particle-photon-oled-screen-and-sd-card-demo/18145 and https://github.com/mikeseeh/photon-demo-oled-sdcard for examples where folks have succeeded.

Requires modification for other screen sizes
With a small change, this library could be adjusted to work with 1.27 inch OLED, and possibly the 0.96 inch OLED breakout boards.

**Wiring**

For hardware SPI (considerably faster), connect the pins as follows:

```
Photon  -> OLED
----------------------
3V3     -> 3Vo (3V)
GND     -> GND (G)

D6      -> DC
D5      -> RESET (R)

A5      -> MOSI (SI)
A3      -> SCK (CL)

A2      -> OLEDCS (OC)
```

DC and RESET may be set to any pin, but the example defaults to D5 & D6.

Any combination of pins may be used for software SPI, but the display will update more slowly.

API documentation
See https://learn.adafruit.com/adafruit-gfx-graphics-library/

## How to use with Particle IDE

-Search for the following library in the IDE: Adafruit_SSD1351_Photon
-Use the example: OLED_test.ino. This will create a new app named oled-test.ino
-Search for the following library in the IDE: ADAFRUIT_MFGFX. Add to your oled-test.ino test file
-Verify the code before running. If you run into any errors, it is likely due to not getting the correct libraries. 
-Run code 

Credits
This is based on a collection of work from other tallented developers, 99.9% of the credit goes to them.

The lion's share of the credit goes to Adafruit - https://github.com/adafruit/Adafruit-SSD1351-library
I started with: https://github.com/nfriedly/Adafruit_SSD1351_Photon
the creator of the above started with: https://github.com/mikeseeh/photon-demo-oled-sdcard
Which I think is based on https://github.com/pkourany/Adafruit_SSD1351_Library/
For full license details, refer to the license file in the library's directory.
