# Bill of Materials

Most of these parts come straight from Adafruit industries. I've tried to
provide links here to the appropriate product pages, but can't guarantee they'll
stay available. Worse, I'm not sure what Digikey or Mouser part numbers they
use, so sourcing equivalents may be a bit of a chore -- especially when it comes
to mechanicals.

I've listed the Adafruit device names in parens where I can.

## Main Body

Obviously you're going to need a DE0-Nano, though any Cyclone IV or V-based dev
board from TerasIC will work. I bought [this one][DE0-Nano] from Adafruit, which
corresponds to [this product page][TerasIC].

Other components you'll need:

  * 1 x [5" 40-pin 800x480 TFT Display without touchscreen (the bare one!)][body1]
  
[DE0-Nano]: https://www.adafruit.com/product/451
[TerasIC]: http://www.terasic.com.tw/cgi-bin/page/archive.pl?Language=English&CategoryNo=139&No=593&PartNo=1
[body1]: https://www.adafruit.com/product/1680

## TFT Driver, Power, and Audio Amp Board

Note: the TFT driver components and circuit design is based upon Adafruit's
[40-pin TFT friend][tft-friend]. The audio amplifier is of my own design.

*Digikey BOM TBD*

  * 2 x [Thin Plastic Speaker w/ Wires - 8ohm 0.25W][audio1]

[tft-friend]: https://github.com/adafruit/Adafruit-40-pin-TFT-Friend
[audio1]: https://www.adafruit.com/product/1891

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
