# SeeedStudio-2CH-EM
**SeeedStudio XIAO 2-Channel Wi-Fi AC Energy Meter** 

A project to update the  SeeedStudio-2CH-EM github files for mainline ESPHome with local modifications for 60Hz AC.

https://wiki.seeedstudio.com/2_channel_wifi_ac_energy_meter/

### Setup repository

`$ git submodule add -b main https://github.com/Seeed-Projects/2-Channel_Energy_Meter_based_on_XIAO_ESP32C6.git`

`$ git submodule add -b test https://github.com/ackPeng/esphome.git`

`$ cd esphome/`

`$ git sparse-checkout set "esphome/components/bl0939"`

`$ cd ..`

`$ git submodule update --init --recursive`

### Add a "secrets.yaml" file to the configuration directory

`$ cat <<- %E%O%T% >./2-Channel_Energy_Meter_based_on_XIAO_ESP32C6/example/secrets.yaml`

`api_key: "" # can get one from https://esphome.io/components/api/`

`ota_password: "strong-unique-password"`

`wifi_ssid: "YourNetworkName"`

`wifi_password: "your-wifi-password"`

`%E%O%T%`

### Build and update binary (Fedora 43)

`$ python3.13 -m venv venv`

`$ ./venv/bin/activate`

`(venv) SeeedStudio-2CH-EM$ esphome -s pwd "$(pwd)" run 2-Channel_Energy_Meter_based_on_XIAO_ESP32C6/example/two_channel_energy_meter_based_on_xiao_esp32c6.yaml --device "<2CH-EM active IP address>"`

esphome -s pwd "$(pwd)" config 2-Channel_Energy_Meter_based_on_XIAO_ESP32C6/example/two_channel_energy_meter_based_on_xiao_esp32c6.yaml
esphome -s pwd "$(pwd)" run 2-Channel_Energy_Meter_based_on_XIAO_ESP32C6/example/two_channel_energy_meter_based_on_xiao_esp32c6.yaml --device 192.168.64.244
