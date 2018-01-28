# Bill of Materials

Most of these parts come straight from Adafruit industries. I've tried to
provide links here to the appropriate product pages, but can't guarantee they'll
stay available. Worse, I'm not sure what Digikey or Mouser part numbers they
use, so sourcing equivalents may be a bit of a chore -- especially when it comes
to mechanicals.

I've listed the Adafruit device names in parens where I can.

## Controllers (Left and Right are identical)

Quantities listed are *per controller*.

  * 5 x [Omron 12mm Tactile Switches (B3F-40xx)][cont1]
  * 1 x [Analog 2-axis Thumb Joystick with Select Button (JOYSTICK)][cont2]
  * 1 x [1x10 0.1" right angle male headers][cont3]

[cont1]: https://www.adafruit.com/product/1009
[cont2]: https://www.adafruit.com/product/512
[cont3]: https://www.adafruit.com/product/1540

### Assembly Notes

  * The 0.1" headers should be soldered on the *back* of the board, fingering the
    underside.
  * Use some form of ribbon cable or jumper cable with 0.1"-style connectors on
    each end. Ideally in something like a 2x6 terminal block one end to make it
    easier to plug into the DE0-Nano. Using [jumper cables like these][jumpers]
    will work, too.
    
[jumpers]: https://www.adafruit.com/product/1950

### Circuit Notes

The buttons are designed to short to `GND` when pressed, including the switch
built into the analog joystick. To make this work properly, however, you need to
configure the GPIOs in the FPGA to turn on their pull up resistors.

The `JOY_V` and `JOY_H` lines are analog and will require connections to the ADC
built into the DE0-Nano.
