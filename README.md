# Sensirion I2C SCD30 Arduino Library

This document explains how to set up a  SCD30 sensor to run on a Arduino

<center><img src="images/sensor_scd30_image.jpg" width="300px"></center>

Click [here](https://sensirion.com/products/catalog/SCD30/) to learn more about the Sensirion SCD30 sensor.



The default I²C address of [SCD30](https://sensirion.com/products/catalog/SCD30/) is **0x61**.



## Setup Guide

### Connecting the Sensor

Your sensor has the 5 different pins you need to connect to your Arduino Board: VDD, GND, SCL, SDA, SEL.
Use the following pins to connect your SCD30:

<img src="images/scd30_pinout.jpg" width="300px">

| *Pin* | *Cable Color* | *Name* | *Description*  | *Comments* |
|-------|---------------|:------:|----------------|------------|
| 1 | red |VDD | Supply Voltage | 3.3 to 5.5V
| 2 | black |GND | Ground | 
| 3 | yellow |SCL | I2C: Serial clock input | 
| 4 | green |SDA | I2C: Serial data input / output | 
| 5 |  |RDY | High when data is available | do not connect
| 6 |  |PWM |  | do not connect
| 7 | blue |SEL | Interface select | Pull to ground or floating for I2c

You can find the pinout for specific boards under following links:
* [Arduino Uno](pinouts/arduino-uno-rev3.md)
* [Arduino Nano](pinouts/arduino-nano.md)
* [Arduino Micro](pinouts/arduino-micro.md)
* [Arduino Mega 2560](pinouts/arduino-mega-2560-rev3.md)
* [ESP32 DevKitC](pinouts/esp32-devkitc.md)

### Installation of Arduino

This library can be installed using the Arduino Library manager:
Start the [Arduino IDE](http://www.arduino.cc/en/main/software) and open
the Library Manager via

    Sketch => Include Library => Manage Libraries...

Search for the `Sensririon I2C SCD30` library in the `Filter
your search...` field and install it by clicking the `install` button.

If you cannot find it in the library manager, download the latest release as .zip file 
and add it to your [Arduino IDE](http://www.arduino.cc/en/main/software) via

	Sketch => Include Library => Add .ZIP Library...

Don't forget to **install the dependencies** listed below the same way via library 
manager or `Add .ZIP Library`

#### Dependencies

* [Sensirion Core](https://github.com/Sensirion/arduino-core)


## Quick Start

1. Connect the SCD30 Sensor to your Arduino board's standard
   I2C bus. Check the pinout of your Arduino board to find the correct pins.
   The pinout of the SCD30 Sensor is described above.

   The recommended voltage is 3.3V.

2. Open the `exampleUsage` sample project within the Arduino IDE via the application menu

		File => Examples => Sensirion I2C SCD30 => exampleUsage


3. Click the `Upload` button in the Arduino IDE or

		Sketch => Upload

4. When the upload process has finished, open the `Serial Monitor` or `Serial
   Plotter` via the `Tools` menu to observe the measurement values. Note that
   the `Baud Rate` in the corresponding window has to be set to `115200 baud`.

## Contributing

**Contributions are welcome!**

We develop and test this driver using our company internal tools (version
control, continuous integration, code review etc.) and automatically
synchronize the master branch with GitHub. But this doesn't mean that we don't
respond to issues or don't accept pull requests on GitHub. In fact, you're very
welcome to open issues or create pull requests :)

This Sensirion library uses
[`clang-format`](https://releases.llvm.org/download.html) to standardize the
formatting of all our `.cpp` and `.h` files. Make sure your contributions are
formatted accordingly:

The `-i` flag will apply the format changes to the files listed.

```bash
clang-format -i src/*.cpp src/*.h
```

Note that differences from this formatting will result in a failed build until
they are fixed.


## License

See [LICENSE](LICENSE).
