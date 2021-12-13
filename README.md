# SSD1306-lib
Library for SSD1306 displays, currently for STM32 processors using I2C.
----
## Description
Basic library for SSD1306 display, includes communication, GRAM writing, contrast setting and basic drawing tools (pixels, lines, characters, strings, lines, rectangles). Scrolling is also supported.

----
## Overview
In addition to basic support, some support for undocumented features is also given here like setting control voltages to undocumented settings (though encouraged in datasheet), drawing to GRAM even when scrolling is used (just stop the scrolling, write the updated part of screen without the part that is scrolling (it is good idea to align the scrolling area to "pages" - see datasheet for what pages stand for)). Only display model UG2864KSWEG01 is supported, but other REAL SSD1306 displays should only differ in direction of row/column sequencing - can be easily worked out by flipping the image (supported in the driver).

----
## Features
### Basic features
* I2C interface
* Command sending
* Buffered framebuffer (requires 1 kB of RAM)
* Fast page sending
* Whole GRAM sending using page sending
* HW scrolling
* Image mirroring, inverting etc.
### Drawing primitives
* Pixel
* Line
* Rectangle
* Chars
* Strings
### Assisting functions
* Easy init functions
* Clearing the display buffer
* Scrolling toggling
* Contrast setting
* Moving part of framebuffer one pixel up for SW scrolling

----
## Porting
You need to rewrite several functions to port this library to anything other than STM32 with SPD libraries. However, the functions are well documented enough so it should be simple to rewrite it for any platform. All numbers use portable formats.

----
## Example of use
[See this project](https://github.com/MR-DOS/TDR_diploma_thesis/blob/master/Firmware/src/board.c)

---
## References
[Datasheet](https://cdn-shop.adafruit.com/datasheets/UG-2864HSWEG01.pdf)
