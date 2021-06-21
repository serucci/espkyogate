# ESPhome for BENTEL KYO32G
[![buy me a coffee](https://img.shields.io/badge/support-buymeacoffee-222222.svg?style=flat-square)](https://www.buymeacoffee.com/lorenzodeluca)

Serial Bridge for **Bentel Kyo32G Alarm Central**, based on **ESP8266** Board and **ESPHome** Open Source Firmware.
Thanks to @dario81 for initial porting to ESPHome.

> **disclaimer** This software was developed by analyzing serial messages from/to central, it was not sponsored or officially supported by **Bentel**

If someone from **Bentel** would like to contribute or collaborate please contact me at [me@lorenzodeluca.dev](mailto:me@lorenzodeluca.dev?subject=[GitHub]ESPKyoGate)

## Hardware Connections
-------------
As board I used a **WeMos D1 Mini** (https://it.aliexpress.com/item/32651747570.html) but any board based on ESP8266 should be fine.

![ESP Wiring](https://raw.githubusercontent.com/lorenzo-deluca/ESPKyo32Gate/master/images/wiring.png)
![ESP Connections](https://raw.githubusercontent.com/lorenzo-deluca/ESPKyo32Gate/master/images/ESP-Connections.jpg)

In order to connect to the serial port of the Kyo32 Unit I recommend a connector based on **MAX3232** chip, like this https://it.aliexpress.com/item/32722395554.html
This connector should be connected to the classic **TX/RX of the ESP board** and to the power supply (GND, 5V) on WeMos.

The WeMos can be powered with USB directly from the 12V output of the control unit by connecting any 12V->USB converter.

Which I recommend because in this way, even in case of power failure, the ESP is powered by the battery of the control unit.

## Firmware Preparation
The file `espkyogate_configuration.yaml` is already present in this repo, 
I suggest you start from this.

Set your WiFi ssid and password in `wifi` section.

Set `uart` settings in base depending on the board you use, example file is for Wemos D1 mini.
Finally edit `binary_sensors` you want to see on your Home Assistant as configured in the example file.

### Build and Upload Firmware

#### With ESPHome 
This way is the easiest, just copy the files from this repository to the esphome folder, edit the `espkyogate_configuration.yaml` file as above, upload and see if everything works from the logs.
You should see something similar.
![ESPHomeLogs](https://raw.githubusercontent.com/lorenzo-deluca/ESPKyo32Gate/master/images/ESPHomeLogs.png)

#### From esphome command line
`python3 -m esphome espkyogate_configuration.yaml compile`
`python3 -m esphome espkyogate_configuration.yaml run`

##### Check logs
See logs with this command 
`python3 -m esphome espkyogate_configuration.yaml logs`

Output should be the same as above

# Usage



## License
GNU AGPLv3 © [Lorenzo De Luca][https://lorenzodeluca.dev]
