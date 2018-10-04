# LiquidCrystal_I2C

This is fast Arduino library for HD44780 LCD display and its clones. Operates in 4-bit mode via I²C bus with 8-bit I/O expander PCF8574/PCF8574A.

The 99.9% of all I²C backpacks from eBay connected like this:

PCF8574 ports.....LCD pins
P0................4/RS
P1................5/RW
P2................6/En
P3................16/BACKLIGHT LED-, turn-on level HIGH/POSITIVE
P4................11/DB4
P5................12/DB5
P6................13/DB6
P7................14/DB7

The initialization string:
- LiquidCrystal_I2C lcd(PCF8574_ADDR_A21_A11_A01, 4, 5, 6, 16, 11, 12, 13, 14, POSITIVE);

But what if your I²C backpack is different? The LCD pin 4/RS connected to PCF8574 port P6 & LCD pin 13/DB6 connected to PCF8574 port P0.
P0................13/DB6
P1................5/RW
P2................6/En
P3................16/BACKLIGHT LED-, turn-on level HIGH/POSITIVE
P4................11/DB4
P5................12/DB5
P6................4/RS
P7................14/DB7

The initialization string:
-LiquidCrystal_I2C lcd(PCF8574_ADDR_A21_A11_A01, 13, 5, 6, 16, 11, 12, 4, 14, POSITIVE);


Supports:

- Arduino AVR
- Arduino ESP8266
- Arduino ESP32
- Arduino STM32
