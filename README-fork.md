# SeeedStudio-2CH-EM
#### **SeeedStudio XIAO 2-Channel Wi-Fi AC Energy Meter** 

A project to update the  SeeedStudio-2CH-EM github files for mainline ESPHome with local modifications for 60Hz AC.

https://wiki.seeedstudio.com/2_channel_wifi_ac_energy_meter/

#### Changes to sensor bl0939 platform ...

- mode: "current_transformer_mode"
- frequency: "60Hz"

### Configure and build

##### Add a "secrets.yaml" file to the configuration directory

`$ cat <<- %E%O%T% >./2-Channel_Energy_Meter_based_on_XIAO_ESP32C6/example/secrets.yaml`
`api_key: "" # can get one from https://esphome.io/components/api/`
`ota_password: "strong-unique-password"`
`wifi_ssid: "YourNetworkName"`
`wifi_password: "your-wifi-password"`
`%E%O%T%`

### Install ESPHome (Fedora 43)

`$ python3.13 -m venv venv`
`$ ./venv/bin/activate`
`(venv) SeeedStudio-2CH-EM$ pip3 install esphome`
`(venv) SeeedStudio-2CH-EM$`

Check config ...

`(venv) SeeedStudio-2CH-EM$ esphome -s pwd "$(pwd)" clean-all example/two_channel_energy_meter_based_on_xiao_esp32c6.yaml`

Build and install ...

`(venv) SeeedStudio-2CH-EM$ esphome -s pwd "$(pwd)" run example/two_channel_energy_meter_based_on_xiao_esp32c6.yaml --device "<2CH-EM active IP address>"`

