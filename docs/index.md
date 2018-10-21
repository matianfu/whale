# Project Whale

This is a hardware project.

This project has three stages.

+ stage 1: prototyping ap6356s wifi/bt combo on sopine baseboard.
+ stage 2: prototyping whole system on custom sopine baseboard.
+ stage 3: product design and verification.

## Stage 1

`ap6356s` is a 2T2R 802.11ac wifi + bluetooth 4.1 module, based on Broadcom BCM4356 chipsets.

The goal of this stage is the verification of system software support for `ap6356s` module, especially the BLE support.



On Sopine baseboard ([datasheet]()) there is a connector for sdio/uart wifi/bt combo. So the first job is to design an extension board and configure the software to support it, both wifi and ble.

KiCAD is used for schematic and layout design.

### datasheets

- [ap6356s](datasheet/AP6356_datasheet_V1.0.pdf)
- [sopine baseboard (local)]()


according to sopine schematic

http://files.pine64.org/doc/SOPINE-A64/SOPINE-A64-Schematic-ver-0.9.pdf

pin name | ball | net name | comment
--|--|--|--
PL2/S-UART-TX | A19 | WL-PMU-EN | alias: WL-REG-ON
PL3/S-UART-RX | E19 | WL-WAKE-AP |
PL4/S-JTAG-MS | A20 | BT-RST-N | no pull-up/pull down
PL5/S-JTAG-CK | D19 | BT-WAKE-AP |
PL6/S-JTAG-DO | B20 | AP-WAKE-BT |
PG0/SDC1-CLK | V21 | WL-SDIO-CLK | with 33ohm dampening resister
PG1/SDC1-CMD | U20 | WL-SDIO-CMD 
PG2/SDC1-D0 | U19 | WL-SDIO-D0
PG3/SDC1-D1 | V22 | WL-SDIO-D1
PG4/SDC1-D2 | Y21 | WL-SDIO-D2
PG5/SDC1-D3 | W23 | WL-SDIO-D3
PG6/UART1-TX | AB17 | BT-UART-RX | named as module signal name
PG7/UART1-RX | U23 | BT-UART-TX | named as module signal name
PG8/UART1-RTS | AC17 | BT-UART-CTS | named as module signal name
PG9/UART1-CTS | U21 | BT-UART-RTS | named as module signal name


### BOM

1. U1 ampak ap6356s
2. Y1 epson 37.4MHz crystall
3. J1, J2, hirose u.fl connector
4. L1, panasonic ELL4G4R7N
5. C1/C2, pf capacitor for crystal
6. C3/C5, 4.7uF 0603 x5r 10V
7. C4, 1uF, 0402 x5r 10V
8. R1, 10K 1%, 0402



## Stage 2

Design a baseboard for sopine.

Active Components

1. Sopine module
2. wifi/bt module
3. usb-sata bridge
4. atecc
5. side view white led

Passive Component

1. sodimm socket (204 pin)
2. m.2 socket
3. usb type-c 
4. button (bottom)
5. battery connector
6. ??? rtc battery connector

## Stage 3

not my job. :)





