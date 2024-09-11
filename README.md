# OSAB-Mainboard-v1.0.0
Mainboard for navigation and control of the vessel. Based on the RP2040. This is a prototype design that is not polished or suitable for use by others. It has been made freely available for educational and historical reasons only.

> ***NOTE:* V1.0.0 IS A PROTOTYPE VERSION. It is not recommended for ANY use. V1.0.0 is the only iteration in the V1.x.x series.**

### Features
- RP2040 processor (16MB flash)
- USB-C power and data connector
- SWD debugging port
- Boot select and reset button
- LiPo/Li-Ion backup battery with charger
- Red power indicator LED
- Yellow battery charge indicator LED
- Three blue LEDs (User-programmable, located in a line for optional use as a 3-bit binary status/error code output)
- Two WS2812B RGB LEDs (User-programmable)
- 4x DIP switch array for input (User-programmable)
- E-STOP button connector (JST-PH)
- Leak sensor connectors (two channels, two inputs per channel, JST-PH)
- GPS (PA1616D)
- CR1220 coin cell holder for GPS (retains sat. positions and speeds up reboot)
- LoRa (RFM95CW)
- Connector for Adafruit BNO085 accelerometer/gyro/magnetometer module (JST-SH)
- SD card slot for mission files and data logging
- PWM servo and ESC output (JST-PH)
- CAN-Bus and 12v input (JST-PH)
- MCP25625 CAN-Bus controller/transceiver
- Two MPM3610 buck converters (12v to 5v and 3.3v)
- AP2112K linear voltage regulator for USB input (5v to 3.3v)

### Notes
- LoRa and CAN-Bus controller share SPI1
- Mounting holes don't fit M3 screws, but should fit M2.5 or M2
- DOUBLE CHECK THAT YOUR LiPo/Li-Ion BATTERY HAS BEEN WIRED WITH THE CORRECT POLARITY BEFORE CONNECTING
- Changing the value of R6 sets the charging current for the backup battery (10k = 100mA, 5k = 200mA, 2k = 500mA, 1k = 1000mA)

### Known Issues
- I2C pullup resistors for the BNO085 connector are series resistors, not pullup resistors (oops)
- Diode on the boot select button serves no purpose (originally intended to allow the button to serve as a user-programmable button after bootup, but was not connected due to a lack of available GPIO)
