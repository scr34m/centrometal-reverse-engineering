# Packet structure over serial Communication

Messages starting with 0xBB and ending 0xEE byte

Message structure in general:
- 0 2 action
- 2 1 length
- 3 4 CRC32 - usage indicated separatedly
- 7 1 type
- 8 n data
- n 2 frame checksum

Response message header structure is the same, but CRC32 is calculated with the requesting message length, extra data is filled with zero on calculation.

Action bytes
- 0x80 0x00 motherboard request
- 0x00 0x80 motherboard response
- 0x80 0x71 wifi box request
- 0x71 0x80 wifi box response

## Motherboard packets

### Request 0x07, 0x08, 0x09, 0x0A, 0x0B - Controller query ADC values

- 0 2 action - 0x80 0x00
- 2 1 type - one of 0x07, 0x08, 0x09, 0x0A, 0x0B
- 3 1 GPIO control hi byte
- 4 1 GPIO control lo byte
- 5 1 RPM hi byte
- 5 1 RPM lo byte

Possbile values in type are:
 - 0x07 ADC query for 16 channels
 - 0x08, 0x09, 0x0A, 0x0B for ADC query in 4 channels

### Response 0x07, 0x08, 0x09, 0x0A, 0x0B

-  0  2 0x00 0x80
-  2  1 type was in request
-  3  1 Digital record
-  4 32 ADC records for 16 channels value in hi / lo format when 0x07
-  4  8 ADC records for 0..3 channels value in hi / lo format when 0x08
-  4  8 ADC records for 4..7 channels value in hi / lo format when 0x09
-  4  8 ADC records for 8..11 channels value in hi / lo format when 0x0A
-  4  8 ADC records for 12..15 channels value in hi / lo format when 0x0B
- 36  1 RPM default hi byte, when 0x07
- 37  1 RPM defult lo byte, when 0x07

Digital record 4 bits used:
- 0 PB8 - CMSR50
- 1 PB9 - EXT2 IN
- 2 ADC reading == 0
- 7 PID received

### Request 0x0C - Controller sends GPID

- 0  2 action
- 2  1 0x0C
- 3 26 data ex.: 0x00 0x06 0x00 0x02 0x01 0x32 0x04 0x00 0x2c 0x01 0x14 0x00 0x32 0x00 0x58 0x1b 0x00 0x00 0x00 0x00 0x00 0x00 0x40 0xe7 0x08 0x46

### Response 0x0C

- 0  2 action
- 2  1 0x0c
- 3 26 response

Response it:
- 0   1 0x68
- 1  17 request data 1..17 bytes
- 18  4 firmware crc32 ex.: 0xdb 0x73 0x48 0xee
- 22  4 crc32

## Wifi box packets

### Request 0x0A - Boiler send data

- 0 2 action
- 2 1 length
- 3 4 CRC32
- 7 1 0xa
- 8 2 seq number
- 10 n data

sequence numbers observed:
0 `{~ITYPE":2}`
1 `{~APN":"apn"}`
2 `{~APNUN":"usr"}`
3 `{~APNPA":"pas"}`
4 `{~URL":"portal.centrometal.hr"}`
5 `{~UPORT":1883}`
6 `{~PROT":0}`
7 `{~MQUN":"usr"}`
8 `{~MQPA":"pas"}`
9 `{~MQID":"000"}`
10 `{"~MQPU":"cm.inst.cmpelet"}`
11 `{"~MQSU":"cm.srv.cmpelet"}`
12 `{"~KEY1":"158208e846"}`
13 `{"~KEY2":"65e0158208"}`
14 `{"~KEY3":"e84665e065"}`
15 `{"~KEY4":"e0158208e8"}`
16 `{"~WIFIN":"WiFi network"}`
17 `{"~WIFIPA":"WiFi password"}`
18 `{"~SERVFL":3}`
19 `{"~CUPORT":44300}`
20 `{"~SAVE":""}`
21 `{"wf_req":"?"}`

### Response 0x0A

-  0 2 0x71 0x80
-  2 1 5
-  3 4 CRC32
-  7 1 0xa
-  8 2 message sequence number
- 10 1 internet status info
- 11 1 wifi signal info

### Request 0x0B - Boiler request data

- 0 2 action
- 2 1 length
- 3 4 CRC32
- 7 1 0xa
- 8 2 seq number

### Response 0x0B

-  0 2 0x71 0x80
-  2 1 5 + data length
-  3 4 CRC32
-  7 1 0xb
-  8 2 message sequence number
- 10 1 internet status info
- 11 1 wifi signal info
- 12 n data

0 .. 9 `{"_MQTT_ID":"4EED90D0","_WIFI_VER":"v1.15"}`
10 .. data is empty

### Request 0x0C - Boiler sends data

- 0 2 action
- 2 1 length
- 3 4 CRC32
- 7 1 0xc
- 8 2 seq number
- 10 n data

sequence numbers observed:
0 {1 0 409 409 409 409 OFF 0 10}
1 {1 23 409 409 409 409 OFF 0 10}
2 {2 0 80000000}
3 {2 0 80000000}

### Response 0x0C

-  0 2 0x71 0x80
-  2 1 5
-  3 4 CRC32
-  7 1 0xc
-  8 2 message sequence number
- 10 1 internet status info
- 11 1 wifi signal info

### Request 0x0D - Boiler request data

- 0 2 action
- 2 1 length
- 3 4 CRC32
- 7 1 0xa
- 8 2 seq number

sequence numbers observed: 0, 2, 3, 4

### Response 0x0D

-  0 2 0x71 0x80
-  2 1 5 + data length
-  3 4 CRC32
-  7 1 0xd
-  8 2 message sequence number
- 10 1 internet status info
- 11 1 wifi signal info
- 12 n data
