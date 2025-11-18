# MOtherboard reverse engineering

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

### Resources

- https://github.com/STMicroelectronics/stm32g0xx-hal-driver