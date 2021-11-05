# LightShow
CircuitPython library for the LightShow module

The LightShow module is an 8 pixel by 8 pixel RGB LED matrix driven by 4 74HC595 shift-out registers.  It must be continually updated to display an image.

## Requirements
This library depends on a build of CircuitPython that contains the *_lightshow* shared-module and shared-bindings, as well as changes to support either a timer driven or multicore SPI streamed output.
