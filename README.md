# Official [KiCon 2019](https://kicad-kicon.com/) badge (hardware design)

_(firmware is in another [repository](https://github.com/orsonmmz/kicon19-badge-sw))_

## Features
* Microchip ATSAM4SD16BA (Cortex-M4, up to 120MHz, 160KB RAM, 1MB FLASH, 64-LQFP; [pdf](http://ww1.microchip.com/downloads/en/DeviceDoc/Atmel-11100-32-bit%20Cortex-M4-Microcontroller-SAM4S_Datasheet.pdf))
* 128x64 pixels, 1.2" ([SH1106](https://www.velleman.eu/downloads/29/infosheets/sh1106_datasheet.pdf)) or 0.96" ([SSD1306](https://cdn-shop.adafruit.com/datasheets/SSD1306.pdf)) OLED display (variant with I2C and GND on pin 1)
* USB 2.0 Full-Speed connectivity (including a bootloader)
* I/O header (2x ADC, 2xDAC, I2C, SPI, UART, 3.3V, GND)
* 2 LEDs
* 4 buttons
* 8-pin buffered input for data acquisition
* 20-pin JTAG header

## Documentation
* [Schematics](https://github.com/orsonmmz/kicon19-badge-hw/raw/master/documentation/kicon19-badge.pdf)
* [Gerbers](https://github.com/orsonmmz/kicon19-badge-hw/tree/master/documentation/gerbers)

## Troubleshooting

* JTAG dongle does not recognize the board (measured Vref is very low)
* 3.3V on the I/O capture header (J1) is not connected

The two problems have the same cause: 3.3V is connected to the JTAG pin header to the I/O capture connector via ERASE button, which is not mounted by default. The JTAG header requires also R7 to be mounted. These problems might be resolved by adding the missing connections (see the picture below).

![Missing connections](/documentation/readme/vref.jpg)

## License
Licensed under [CERN OHL v.1.2](https://ohwr.org/cernohl) or later.
