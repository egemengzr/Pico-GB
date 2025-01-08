# RP2040-GB for Pico-GB

This is a fork of the [RP2040-GB Game Boy (DMG) emulator from deltabeard](https://github.com/deltabeard/RP2040-GB). RP2040-GB is a Game Boy (DMG) emulator Peanut-GB on the Raspberry Pi RP2040 microcontroller, using an ILI9225 screen. Runs at more than 70 fps without audio emulation. With frame skip and interlacing, can run at up to 120 fps.

This fork includes changes done by YouMakeTech:
* push buttons support
* overclocking to 266MHz for more accurate framerate (~60 FPS)
* I2S sound support (44.1kHz 16 bits stereo audio)
* SD card support (store roms and save games) + game selection menu
* automatic color palette selection for some games (emulation of Game Boy Color Bootstrap ROM) + manual color palette selection

Pico-GB is a [3d-printed Game Boy emulator handheld gaming console for Raspberry Pi Pico and it's look like BMO](link).

# Videos
* [How to Build a BMO as a Handheld Console](link)
* [Making BMO Handheld Console (Timalapse)](link)

# Hardware
## What you need
* (1x) [Raspberry Pi Pico](https://www.raspberrypi.com/products/raspberry-pi-pico/)
* (1x) [2.2inch ILI9225 176×220 LCD Display Module](https://tr.aliexpress.com/item/1005007465357755.html)
* (1x) [FAT 32 formatted Micro SD card + adapter](https://www.raspberrypi.com/products/sd-cards/) with roms you legally own. Roms must have the .gb extension and must be copied to the root folder.
* (1x) [MAX98357A amplifier](https://amzn.eu/d/cFlT49p)
* (1x) [2W 8ohms speaker]([https://amzn.to/3ikDy6S](https://tr.aliexpress.com/item/4000819227540.html))
* (8x) [Micro Push Button Switch, Momentary Tactile Tact Touch, 6x6x6 mm, 4 pins](https://amzn.to/3dyXBsx)
* (1x) [Solderable Breadboard](https://amzn.to/3lwvfDi)
* (1x) [Mini Switch](https://tr.aliexpress.com/item/1005002512478598.html)
* (1x) 3.7V 1S Battery (I was used 2800mAh)
* (1x) [PCB](link)
* [Dupont Wires Assorted Kit (Male to Female + Male to Male + Female to Female)](https://amzn.to/3HtbvdO)
* [Preformed Breadboard Jumper Wires](https://amzn.to/3rxwVjM)

DISCLAIMER: There are no affiliate links.

## Setting up the hardware
[BMO 3D Files](link)

# Pinout
* UP = GP2
* DOWN = GP3
* LEFT = GP4
* RIGHT = GP5
* BUTTON A = GP6
* BUTTON B = GP7
* SELECT = GP8
* START = GP9
* SD MISO = GP12
* SD CS = GP13
* SD CSK = GP14
* SD MOSI = GP15
* LCD CS = GP17
* LCD CLK = GP18
* LCD SDI = GP19
* LCD RS = GP20
* LCD RST = GP21
* LCD LED = GP22
* MAX98357A DIN = GP26
* MAX98357A BCLK = GP27
* MAX98357A LRC = GP28

# Flashing the firmware
* Download RP2040_GB.uf2 from the [releases page](https://github.com/YouMakeTech/Pico-GB/releases)
* Push and hold the BOOTSEL button on the Pico, then connect to your computer using a micro USB cable. Release BOOTSEL once the drive RPI-RP2 appears on your computer.
* Drag and drop the UF2 file on to the RPI-RP2 drive. The Raspberry Pi Pico will reboot and will now run the emulator.

# Preparing the SD card
The SD card is used to store game roms and save game progress. For this project, you will need a FAT 32 formatted Micro SD card with roms you legally own. Roms must have the .gb extension.

* Insert your SD card in a Windows computer and format it as FAT 32
* Copy your .gb files to the SD card root folder (subfolders are not supported at this time)
* Insert the SD card into the ILI9225 SD card slot using a Micro SD adapter

# Building from source
The [Raspberry Pi Pico SDK](https://github.com/raspberrypi/pico-sdk) is required to build this project. Make sure you are able to compile an [example project](https://github.com/raspberrypi/pico-examples#first--examples) before continuing.

# Known issues and limitations
* No copyrighted games are included with Pico-GB / RP2040-GB. For this project, you will need a FAT 32 formatted Micro SD card with roms you legally own. Roms must have the .gb extension.
* The RP2040-GB emulator is able to run at full speed on the Pico, at the expense of emulation accuracy. Some games may not work as expected or may not work at all. RP2040-GB is still experimental and not all features are guaranteed to work.
* RP2040-GB is only compatible with [original Game Boy DMG games](https://en.wikipedia.org/wiki/List_of_Game_Boy_games) (not compatible with Game Boy Color or Game Boy Advance games)
* Repeatedly flashing your Pico will eventually wear out the flash memory (Pico is qualified for min. 100K flash/erase cycles)
* The emulator overclocks the Pico in order to get the emulator working fast enough. Overclocking can reduce the Pico’s lifespan.
* Use this software and instructions at your own risk! I will not be responsible in any way for any damage to your Pico and/or connected peripherals caused by using this software. I also do not take responsibility in any way when damage is caused to the Pico or display due to incorrect wiring or voltages.

# License
MIT
