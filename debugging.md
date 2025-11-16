# Debugging - self notes on Wifi box

OpenOCD and STM32CubeIDE used for connecting with STLink and debugging with GDB

```
C:\Dev\OpenOCD-20250710-0.12.0\bin>openocd.exe -f ..\share\openocd\scripts\interface\stlink.cfg -f ..\share\openocd\scripts\target\stm32f0x.cfg
C:\ST\STM32CubeIDE_1.19.0\STM32CubeIDE\plugins\com.st.stm32cube.ide.mcu.externaltools.gnu-tools-for-stm32.13.3.rel1.win32_1.0.0.202411081344\tools\bin>arm-none-eabi-gdb.exe firmware.elf

# init
target remote localhost:3333
monitor reset halt
disassemble

restore c:\dev\firmware.bin binary 0x08000000

# bypass watchdog enable
break *0x080075bc
set $pc = 0x080075be
c

# dump memory
x/16xw 0x20000000
```