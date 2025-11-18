# Controller reverse engineering

S29GL06AN90TFI03

## STM32F103ZFT6 Memory map

0x20000000 SRAM
0x08000000 Flash memory

0x4001 2000 - 0x4001 23FF PORT G
0x4001 1C00 - 0x4001 1FFF PORT F
0x4001 1800 - 0x4001 1BFF PORT E
0x4001 1400 - 0x4001 17FF PORT D
0x4001 1000 - 0x4001 13FF PORT C
0x4001 0C00 - 0x4001 0FFF PORT B
0x4001 0800 - 0x4001 0BFF PORT A

768 KB Flash
96 KB SRAM

## PINS

Chip communication
- PA14 - SWCLK
- PA13 - CWDIO

## Serial

Serial commands: 
 - mast.Sla.Com
 - io
 - process
 - counters
 - led
 - readKey
 - alarm
 - regGr
 - rtc
 - pumps
 - conditions
 - puz
 - cleaner
 - kaskada
 - mis
 - pstTest
 - vac
 - lamTune
 - dbg
 - lamtune
 - ms
 - smd
 - txt
 - cmcrc
 - cmts
 - cmtakeover
 - cmrelase
 - cmerase
 - cmdate
 - cmtime
 - cmlam
 - cmcom
 - cmout
 - cminput
 - cminfo
 - pst
 - krs
 - sim
 - kkot
 - vect
 - konf
 - ztr
 - lout
 - spc
 - pne
 - tst1
 - kas
 - reg
 - flg
 - kot
 - mmd
 - vag
 - pf
 - pflg
 - ilog
 - pl
 - tw
 - cyc
 - rs
 - pin
 - prtsc
 - milist
 - memitem
 - midel
 - load
 - save
 - lam
 - io
 - debug
 - st
 - str
 - info
 - erase
 - write
 - read
 - msg
 - pid
 - comcnt
 - alt
 - dbinfo
 - finfo
 - ptest
 - win1
 - errList
 - werr
 - fac
 - err
 - spa
 - epm
 - enm
 - sss
 - ssa
 - tsk
 - time
 - date
 - jez
 - tst
 - sav
 - win
 - rst
 - dfu
 - cd..
 - cd
 - al
 - bar
 - cw
 - dat
 - cmd
 - wr
 - rd
 - init
 - r0
 - r1
 - test
 - line
 - text
 - ts
 - dir
 - putimage