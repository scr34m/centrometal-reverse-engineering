# MOtherboard reverse engineering

- MOC3082, MOC3063 - Zero-Cross Triac Driver Optocoupler
- STM32G070RBT6

## STM32G070RBT6 Memory map

0x20000000 SRAM
0x08000000 Flash memory

0x5000 1800 - 0x4800 17FF GPIOF
0x5000 1400 - 0x4800 13FF GPIOE
0x5000 0C00 - 0x4800 0FFF GPIOD
0x5000 0800 - 0x4800 0BFF GPIOC
0x5000 0400 - 0x4800 07FF GPIOB
0x5000 0000 - 0x4800 03FF GPIOA

128 KB Flash
36 KB SRAM

## PINS

Chip communication
- PA14 - SWCLK
- PA13 - CWDIO

Serial
- PD5 - USART2_TX
- PD6 - USART2_RX

RS485 reading
- PA10 - USART1_RX
- PA9 - USART1_TX

GPIOs (triac numbers counted from line in):
- PB13 SET (1), 1 → PB13 RESET (0): Triac 9 OT1
- PB14 SET, 0 → PB14 RESET: 
- PB15 SET, 0 → PB15 RESET: Triac 8 ON4, Triac 7 OT7
- PC6 SET, 0 → PC6 RESET: Triac 6 OT2
- PC8 SET, 0 → PC8 RESET: Triac 5 OT5
- PD9 SET, 0 → PD9 RESET: Triac 4 OT9
- PD8 SET, 0 → PD8 RESET: Triac 3 OT3
- PD2 SET, 0 → PD2 RESET: Triac 10 OT13
- PD3 SET, 0 → PD3 RESET: 
- PD4 SET, 0 → PD4 RESET: 
- PD5 SET, 0 → PD5 RESET: 
- PB3 SET, 0 → PB3 RESET: Triac 2 OT6
- PB7 SET, 0 → PB7 RESET: 
- PB5 SET, 0 → PB5 RESET: 

Misc:
- PB9 - EXT2 IN

Key:
- PC5

TEMP1:
- PB10 - Boiler
- PA0 - DHW
- PA1 - Buffer 1

TEMP2:
- PA2 - Buffer 2
- PA3 - Spare 1
- PA4 - SPare 2

TEMP3:
- PA5 - Circuit 1
- PA6 - Circuit 2
- PA7 - Outside

COR1:
- PB12 - Pos
- PB0 - Temp

COR2:
- PB11 - Pos 
- PB1 - Temp 

## MQTT

Commands:
- PRD
- PWR
- CMD
- RSTAT
- stamp
- REFRESH
- _MQTT_ID
- _WIFI_VER
- Day_0
- Day_1
- Day_2
- Day_3
- Day_4
- Loc

## Serial

Serial commands: 
 - pid1
 - pid
 - info
 - out
 - in
 - adc
 - fw
 - sp
 - wdg

### Resources

- https://github.com/STMicroelectronics/stm32g0xx-hal-driver