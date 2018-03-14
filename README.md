## Switch Serial Input

Based on [Bert's snowball thrower](https://github.com/bertrandom/snowball-thrower), the final aim of this is to accept commands via serial input and then perform them as a controller, useful for TAS's or TwitchPlays[Switch Game].

This project uses an atmega32u4 based pro micro (available on aliexpress for around £2.70), but will work on a Teensy++ v2.0 (untested), and should work on all [LUFA compatible boards](http://www.fourwalledcubicle.com/files/LUFA/Doc/151115/html/_page__device_support.html).

## Current State

Currently, no serial input is working. However, you can now press more than one button at a time in the hardcoded script, alowing for more complex scripts and allowing the user to more easily adapt it for their own needs. Unfortunately there seems to be a timing limitation, with a minimum of 30 cycles needed between button presses.

There is also a working basic serial implementation [here](https://github.com/ebith/Switch-Fightstick)

## Cloning, Compiling and Flashing

This project requires gcc-avr to compile, head to [Teensy's Page](https://www.pjrc.com/teensy/gcc.html) to find out how to install it for your operating system. If you have any trouble, or it doesn't work, refer to Bert's readme as the compiling method is the same.

To clone the repo, use:

`git clone --recursive https://github.com/Septolum/Switch-Serial-Input`

as LUFA has been included as a git submodule.

To compile, enter the cloned directory in a terminal window and type `make`

To change what board you're compiling for, just change the MCU value in the makefile (case insensetive, use LUFA's board names linked above).

To then upload to your pro micro, follow the flashing part of the guide on [this page](https://deskthority.net/workshop-f7/how-to-use-a-pro-micro-as-a-cheap-controller-converter-like-soarer-s-t8448.html) and use `Joystick.hex` as your filename
