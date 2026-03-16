# Firmware for Waveshare ESP32-S3 RS485 CAN to integrate Hoval TopTronic E into Home Assistant


## Acknowledgements

This project originated as a fork of [Original Project](https://github.com/nliaudat/esp_canbus) 
by [nliaudat]. It has since diverged significantly and is maintained independently.


    
## Functionalities : 
This firmware has been tailored to run on a WaveShare ESP32-S3 RS485 CAN Board. This is an off the shelf IoT CAN transceiver which has DIN rail mount. It can be neatly mounted inside the Hoval TopTronic E casing. It cost about 20CHF so this is a much cheaper option than the official Hoval HomeAssistant solution. (4-500CHF)
* The software runs under esphome to be easy to customize and linked with https://www.home-assistant.io 
* Power is taken from CanBus 12V 

## Firmware

<p align="center">
    <img src="esphome/home_assistant.png" width=80% />
    <br />
    <i>web interface at http://canbus.local/</i>
</p>

### Features

* Powered by [ESPHome](https://esphome.io/)
* Webserver enabled at [canbus.local](http://canbus.local/)
* Automatically recognized by [Home Assistant](https://www.home-assistant.io/)
* Forked from nliaudat/esp_canbus *

### Installation

#### Requirements

Make sure you have Python and ESPHome installed. <br />
To install ESPHome you can follow the [manual installation guide](https://esphome.io/guides/installing_esphome) or use [Docker](https://esphome.io/guides/getting_started_command_line#installation).

You can validate your installation by running

```bash
> esphome version
Version: 2023.11.6
```

#### Firmware configuration

Enter your Wifi SSID and password in `secrets.yaml`.<br />

3. Select your desired presets. All presets are located at [`esphome/src/preset`](https://github.com/nliaudat/esp_canbus/tree/main/esphome/src/preset). <br /> e.g. to select the HV preset in French:

```yaml
packages:
  # ...
  hv_sensors: !include src/preset/HV/sensors_fr.yaml
  hv_inputs: !include src/preset/HV/inputs_fr.yaml
```

If you want to create your own preset or need other datapoints have a look at [`esphome/hoval_data_processing`](https://github.com/nliaudat/esp_canbus/tree/main/esphome/hoval_data_processing)

#### Flash the firmware

Connect your ESP32 via USB to your computer. (Only required for the first time, subsequent installations can be done over WiFi) <br />
Then run `esphome run config.yaml`

## Note: 
Not maintained for HomeVent 



## Licence: 
* Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC-BY-NC-SA)
* No commercial use
