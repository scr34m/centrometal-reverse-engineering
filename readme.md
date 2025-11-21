# Centrometal reverse engineering

The boiler or stove system is a Centrometal Pellet Set 25KW with this 3 module

- [Wifi Box](wifibox.md) allows you to monitor and send commands in, this communicates over [MQTT](mqtt.md) with the portal system
- [Motherboard](motherboard.md) has all the sensors and drivers for the ports
- [Controller](controller.md) CPREG-Touch is a touch screen and coordinates

All the modules are connected with a [RS485 bus](bus.md) which is a serial communication on 57600 baud speed, connection form is RJ42 with A, B, GND and 12V lines. They have 2 ports usally one for serial and one debugging aka. SWD for the STM microcontroller.

## Resources

- https://www.youtube.com/watch?v=q4CxE5P6RUE
- https://github.com/leveldown-security/SVD-Loader-Ghidra
- https://github.com/cmsis-svd/cmsis-svd-data/blob/main/data/STMicro/STM32F0xx.svd
- https://github.com/cmsis-svd/cmsis-svd-data/blob/main/data/STMicro/STM32F103xx.svd
- https://github.com/cmsis-svd/cmsis-svd-data/blob/main/data/STMicro/STM32G070.svd
- https://stm32-base.org/guides/connecting-your-debugger.html
