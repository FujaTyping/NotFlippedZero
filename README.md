# NotFlippedZero (Wifi penetration tool)
It provides some common functionality that is commonly used in Wi-Fi attacks and makes implementing new attacks a bit simpler

## Install & Build & Flash
- ESP-IDF 4.1 `(commit 5ef1b390026270503634ac3ec9f1ec2e364e23b2)` (ESP32)
- ESP-IDF 4.4.8 [Release](https://github.com/espressif/esp-idf/releases/tag/v4.4.8) (ESP32C3 , ESP32)
```
idf.py build
```
```
idf.py -p [PORT] flash
```

## Flashing without build
- [ESPTOOL.PY](https://github.com/espressif/esptool) (Require python)
```
esptool.py -p [PORT] -b 115200 --after hard_reset write_flash --flash_mode dio --flash_freq 40m --flash_size detect 0x8000 build/partition_table/partition-table.bin 0x1000 build/bootloader/bootloader.bin 0x10000 build/esp32-wifi-penetration-tool.bin
```

## Default board
This project set default support board is **ESP32C3**
- Change board to other board
Must match ESP-IDF version
>- ESP-IDF 4.1 `(commit 5ef1b390026270503634ac3ec9f1ec2e364e23b2)` (ESP32)
> - ESP-IDF 4.4.8 [Release](https://github.com/espressif/esp-idf/releases/tag/v4.4.8) (ESP32C3 , ESP32)
```
idf.py set-target [BOARD_NAME]
```
```
idf.py build
```

## Using the tool
1. After flashing connect the the ESP32 via **Wi-Fi**
2. Default **SSID** `NotFlippedZero` and **PASSWORD** `zer0admin`
3. After connected to the ESP32 go to your browser then type `192.168.4.1` (http) to access the pannel
4. Start using the tool

## SDK menu
![image](https://github.com/user-attachments/assets/866e000c-3118-4be7-9e5e-600d89079d83)
- ESP-IDF 4.1 `(commit 5ef1b390026270503634ac3ec9f1ec2e364e23b2)`
```
idf.py menuconfig
```
To config the wifi components go to the `Component config --> Wi-Fi Controller`

# 🙏🏻 Big thank to [Risinek](https://github.com/risinek/esp32-wifi-penetration-tool) for original code !
