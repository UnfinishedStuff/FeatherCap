# FeatherCap
PCB for pairing Adafruit Feather boards with Raspberry Pi HATs

![FeatherCap board](/FeatherCap.jpg)

This repo contains the files for the FeatherCap, a PCB I put together to connect Adafruit Feather microcontroller boards with Raspberry Pi HAT-format boards.  Just be aware that so far this has had fairly minimal testing so may still have some issues.  `FeatherCapv0.2_Gerber.zip` is the zipped file of the board which can be submitted as-is to a PCB fab, or you should be able to open the files in PCB design programs like Kicad, Eagle etc..  I got these made by Aisler.net at ~£18 for 3 boards, but should work at any of the common fabs.

The SPI, I2C, and UART pins on the Feather socket and 2x20 Pi header are hard-wired to each other, because these should be standard across Feather and Pi boards.  The 5V pins on the Pi header are hard-wired to the Feather's vUSB pin, and so should take power directly from the USB port.  The 3v3 pins on the Pi header are hard-wired to the 3v3 pin on the Feather layout (*be aware of the amount of current the Feather can supply*).  All ground pins on the Feather header and Pi header are connected.  Please note, if you power the Feather with a LiPo battery there will be no source of 5V for your HAT.

Between the Feather and HAT is a double row of pins where the Feather and HAT pins meet.  These are intended to mostly be connected with jumpers, and each side of the double row is labelled with the corresponding Feather or Pi pin (the Feather pins were taken from the Feather M4 Express which was used when I was designing this, and the Pi pins are in BCM format).  To the right of this is another set of 6 pins: these are 5 pins on the Pi header which weren't paired directly with a Feather pin because the Feather has fewer GPIO pins than the Raspberry Pi, and one non-connected pin.
