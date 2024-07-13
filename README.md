# NotFlippedZero (Wifi penetration tool)
It provides some common functionality that is commonly used in Wi-Fi attacks and makes implementing new attacks a bit simpler

## Install & Build & Flash
- ESP-IDF 4.1 `(commit 5ef1b390026270503634ac3ec9f1ec2e364e23b2)`
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

## SDK menu
![image](https://github.com/user-attachments/assets/866e000c-3118-4be7-9e5e-600d89079d83)
- ESP-IDF 4.1 `(commit 5ef1b390026270503634ac3ec9f1ec2e364e23b2)`
```
idf.py menuconfig
```
To config the components go to the `Component config`

# 🙏🏻 Big thank for [Risinek](https://github.com/risinek/esp32-wifi-penetration-tool) for original code !
