UART HCI Bluetooth Module
=========================

There is a Bluetooth 4.2 dual-mode controller inside the ESP32 chip, which can use UART(H4) as HCI IO.

## Pinmap

| HOST  | RX | TX | CTS | RTS |
| :---- | -: | -: | --: | --: |
| ESP32 | TX | RX | RTS | CTS |
| Pin   |  5 | 18 |  19 |  23 |

* HCI UART protocol: `H4`
* HCI UART baudrate: `921600 bps`

## Preparing

### Obtain the source

```
git clone --recursive https://github.com/redchenjs/uart_hci_bluetooth_module_esp32.git
```

### Update an existing repository

```
git pull
git submodule update --init --recursive
```

### Setup the tools

```
./esp-idf/install.sh
```

## Building

### Setup the environment variables

```
export IDF_PATH=$PWD/esp-idf
source ./esp-idf/export.sh
```

### Flash & Monitor

```
idf.py flash monitor
```

## Attach device to system

```
btattach -B /dev/ttyX -P h4 -S 921600
```
