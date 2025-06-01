### ESP32
* The ESP32-C3-MINI boards expose USB and have really good documentation
* ESP32 is generally cheaper and better than ESP8266 (faster CPU, BLE, more RAM/flash), and ESP8266 is not recommended for new designs
* The ESP32-WROOM boards don't expose the USB interface of the ESP32, which would then require an additional USB-to-UART component adding cost

### USB-C Connector
* TYPE-C-31-M-12 chosen due to providing USB 2.0 data lines in an easy-to-manufacture package

### ESD Protection
* USBLC6-2 chosen due to being a known component specifically designed for USB 2.0
* Layout optimized to be close to USB-C connector, and have short traces for data and VBUS/GND
* 100nF between VBUS and GND was missed, but there's one not far away for the LDO which should be sufficient
