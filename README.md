# esp32-Firmware-Marauder
Firmware for cyd



Installation Method
Web Flasher Method (Recommended)
Go to the CYM Web Flasher
Hold BOOT on your device, click "Connect" and select
Choose the appropriate Model and Version
Click "Program" to start flashing

![sc00000](https://github.com/user-attachments/assets/0bcd14e3-a52e-43d0-b5b9-530482234f27)

link : https://fr4nkfletcher.github.io/Adafruit_WebSerial_ESPTool/
Troubleshooting:
If issues arise, try the following steps:

Unplug and restart your CYD module
Hold RST, tap BOOT, release RST (the screen should go blank)
Refresh the Web Flasher page and click "Connect"
For further details, check out the Web Flasher repository.

Alternatively, you can flash using esptool.py by:

cd ~
git clone https://github.com/Fr4nkFletcher/Adafruit_WebSerial_ESPTool
esptool.py --port /dev/YOURSERIALPORT write_flash 0x1000 ~/Adafruit_WebSerial_ESPTool/resources/STATIC/M/CYD/esp32_marauder.ino.bootloader.bin \
0x8000 ~/Adafruit_WebSerial_ESPTool/resources/STATIC/M/CYD/esp32_marauder.ino.partitions.bin \
0x10000 ~/Adafruit_WebSerial_ESPTool/resources/CURRENT/esp32_marauder_ofyourchoice.bin
Manual Arduino IDE Method
Set up your Arduino environment following the ESP32 Marauder Arduino IDE Setup Guide
Update your platform.txt
Add the necessary libraries to your Arduino libraries folder
Set the upload speed to 115200 in the Arduino IDE (tested on version 1.8.19)
Upload the firmware to your CYD module
For a step-by-step guide, refer to Smoochiee's tutorial

Compatibility
The project has been successfully tested on:

2.4" Resistive Touch
2.4" Resistive Touch Guition
2.8" Resistive MicroUSB-only
2.8" Resistive MicroUSB/Type-C 2USB
3.2" Resistive Touch
3.5" Resistive Touch
No hardware modifications are required, thanks to @ggaljoen's fork of the TFT_eSPI library

GPS Functionality
GPS functionality is fully supported via the 4-pin connector near the MicroUSB port. For a list of compatible GPS hardware, refer to the official wiki

GPS	->	CYD
VCC	->	VIN
GND	->	GND
TX	->	TX
RX	->	RX
Note: On 2.4" and 3.5" models swap RX/TX

****
