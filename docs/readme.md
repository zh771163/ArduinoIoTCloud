# ArduinoIoTCloud

The ArduinoIoTCloud library is the central element of the firmware enabling certain Arduino boards to connect to the [Arduino IoT Cloud](https://create.arduino.cc/iot/).

- To get started, check out the [official documentation](https://docs.arduino.cc/arduino-cloud/)
- For source code, check out the [GitHub repository](https://github.com/arduino-libraries/ArduinoIoTCloud)


## TCP / LPWAN

Depending on what type of connection is used (TCP/LPWAN), either the `ArduinoIoTCloudTCP` or `ArduinoIoTCloudLPWAN` base classes are initialized. This specification is done in the Arduino IoT Cloud's "Thing" interface, and is reflected in the automatically generated `thingProperties.h` file.

- If a board is configured as a **TCP** device, it will automatically include the `ArduinoIoTCloudTCP.h` file, and methods of the `ArduinoIoTCloudTCP` class will be made available. This is the most common option.
- If a board is configured as an **LPWAN** device, it will instead include the `ArduinoIoTCloudLPWAN.h` file, and methods of the `ArduinoIoTCloudLPWAN` class will be made available. 

As a result, functions such as `begin()`, `update()`, `connected()` and `printDebugInfo()` are documented under each corresponding class.

## Connection Handler Library

When the library is initalized via the `begin()` function, it will choose the specified **connection handler**, which is automatically added to your `thingProperties.h` file when configuring a Thing.

The connection handler is done via another library, [Arduino_ConnectionHandler](https://github.com/arduino-libraries/Arduino_ConnectionHandler), which supports Wi-Fi®, GSM, NB-IoT, LoRa® & Ethernet.
