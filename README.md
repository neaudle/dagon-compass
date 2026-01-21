# dagon-compass

A cute little tilt compensated compass with a CMPS14 and an esp32, featuring my dagon [Thistle](https://i.imgur.com/QAG7xas.jpeg).

## Video: 

https://github.com/user-attachments/assets/2e4ac9ee-e58d-4070-ac7a-0b809c0fd679

---

## Hardware you need

* Wemos D1 mini (ESP8266)
* CMPS14 (The CMPS12 looks like it'd work based on the addresses, but I don't have one to test)
* 128×64 SSD1306 0.96" OLED (Important: get the 7 pin SPI version!)


## How to upload it to the D1 Mini

Visual Studio Code with the Platformio extension is the easiest; just open the project folder in PlatformIO and hit upload.

Everything important is in /src/main.cpp and /src/platformio.ini.

### How to make your own custom images
Use [image2cpp](https://javl.github.io/image2cpp/) with 64x64 black and white .bmp files.

By default there are 8 directions:　N, NW, W、SW, S, SE, E, NE

### OLED wiring to the Wemos D1 Mini (SPI)

* GND <-> GND
* VCC <-> 3V3
* D0 <-> D5 (GPIO14)
* D1 <-> D7 (GPIO13)
* CS <-> D8 (GPIO15)
* DC <-> D4 (GPIO2)
* RST <-> D0 (GPIO16)

### CMPS14 Wiring to the Wemos D1 Mini (I²C)

* SDA <-> D2 (GPIO4)
* SCL <-> D1 (GPIO5
* VCC <-> 3V3 or 5V (CMPS14 seems to like ~5v a smidge better)
* GND <-> GND

### Libraries:
* [Adafruit SSD1306](https://github.com/adafruit/Adafruit_SSD1306)
* [Adafruit GFX](https://github.com/adafruit/Adafruit-GFX-Library)
* [Arduino Core / Wire](https://github.com/arduino/ArduinoCore-avr/blob/master/libraries/Wire/src/Wire.h)
