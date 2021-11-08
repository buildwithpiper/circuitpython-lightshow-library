# LightShow
CircuitPython library for the LightShow module

The LightShow module is an 8 pixel by 8 pixel RGB LED matrix driven by four 74HC595 shift-out registers.  It must be continually updated to display an image.

## Requirements
This library depends on a build of CircuitPython that contains the *_lightshow* shared-module and shared-bindings, as well as changes to support either a timer driven or multicore SPI streamed output.

## Known Limitations
On the RP2040 MCU, SPI streaming is handled by the second unused processor core (core1).  As a result, it commands the SPI pins, and at this time, there are no lockouts or notifications to CircuitPython that those pins are in use.  If CircuitPython tries to use them, the behavior is unknown.  The SPI on the RP2040 is streamed out through a FIFO, so the most likley result is that bits written out to the SPI by core0 will simply be mixed in with bytes written by core1 - resulting in nonsense bytes to any perpheral that may be attached.
