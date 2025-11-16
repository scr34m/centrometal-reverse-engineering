# Wifi Box reverse engineering

An "expensive" extra device after you paid a good amount for a boiler, this small IoT device will be used as a gateway between boiler(s) and Centrometal platform.

## Components

- STM32F070CBT6 - ARM®-based 32-bit MCU, up to 128 KB Flash, USB FS 2.0, 11 timers, ADC, communication interfaces, 2.4 - 3.6 V
- ST3485EBDR - 3.3 V powered, 15 kV ESD protected, up to 12 Mbps RS-485/RS-422 transceiver
- TPS54232 - 2-A, 28-V, 1-MHz, Step-Down DC-DC Converter With Eco-Mode™
- ESPWROOM-02 - Wifi board

## RJ45 socket

- 1 orange white - A
- 2 orange - B
- 3 green white - GND
- 4 blue - GND
- 5 blue white - 12V
- 6 green - 12V
- 7 brown white - GND
- 8 brown - GND

Serial communication is used over the UTP wire on 57600 baud with modbus

## STM32F070CBT6 Memory map

0x2000000 SRAM
0x0800000 Flash memory

0x4800 1400 - 0x4800 17FF GPIOF
0x4800 0C00 - 0x4800 0FFF GPIOD
0x4800 0800 - 0x4800 0BFF GPIOC
0x4800 0400 - 0x4800 07FF GPIOB
0x4800 0000 - 0x4800 03FF GPIOA

128 KB Flash
16 KB SRAM

## PINS

Chip communication
- PA14 - SWCLK
- PA13 - CWDIO

Serial out
- PB11 - USART3_RX, EVENTOUT, I2C2_SDA
- PB10 - SPI2_SCK, USART3_TX

RS485 reading
- PA10 - RO - USART1_RX, TIM1_CH3, TIM17_BKIN, I2C1_SDA(3)
- PA9 - DI - USART1_TX, TIM1_CH2, TIM15_BKIN, I2C1_SCL(3)
- PA8 - DE / RE  - USART1_CK, TIM1_CH1, EVENTOUT, MCO
