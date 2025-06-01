### ESP32
* The ESP32-C3-MINI boards expose USB and have really good documentation
* ESP32 is generally cheaper and better than ESP8266 (faster CPU, BLE, more RAM/flash), and ESP8266 is not recommended for new designs
* The ESP32-WROOM boards don't expose the USB interface of the ESP32, which would then require an additional USB-to-UART component adding cost
* TODO: In the datasheet it says "USB Serial/JTAG Controller can also force the chip into Joint Download Boot mode from SPI Boot mode, as well as force the chip into SPI Boot mode from Joint Download Boot mode. For detailed information, please refer to Chapter 30 USB Serial/JTAG Controller (USB_SERIAL_JTAG).", can this be used to avoid buttons entirely? It would cut costs and make the device easier to use.

### USB-C Connector
* TYPE-C-31-M-12, provides USB 2.0 data lines in an easy-to-manufacture package

### ESD Protection
* USBLC6-2, common component specifically designed for USB 2.0
* Layout optimized to be close to USB-C connector, and have short traces for data and VBUS/GND
* 100nF between VBUS and GND was missed, but there's one not far away for the LDO which should be sufficient

### Level Shifter
* MCP1416, common component in a small package, enough current output for longer LED strip data lines
* ~SN74LVC1T45DBVR, only has 24mA output current, might not be enough for longer LED strip data lines~

### LDO
* AZ1117-3.3, common component, low enough dropout for 5V -> 3.3V, high enough current for ESP32, modern design that is compatible with low ESR ceramic caps
* ~AMS1117-3.3, common component, low enough dropout for 5V -> 3.3V, high enough current for ESP32, however it requires a tantalum cap on the output which is annoying~
