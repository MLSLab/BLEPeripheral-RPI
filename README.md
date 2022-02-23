# BLEPeripheral-RPI
Using a RaspberryPI as a BLE peripheral

**Data Flow**<br>
BLE Central → BLE peripheral → BLE Central 
 
## RaspberryPI Setting

[Raspberry Pi OS](https://www.raspberrypi.com/software/operating-systems/)

## RaspberryPI Advertising Setting 

```
bluetoothctl 
[bluetooth]# agent on 
[bluetooth]# default-agent # 기본 에이전트로 등록. 
[bluetooth]# menu advertise 
[bluetooth]# manufacturer 0xffff 0x12 0x34  # 일단 임의의 값?
[bluetooth]# name HYERIN001
[bluetooth]# advertise on
[bluetooth]# discoverable on
```
## GATT Server 동작 예시
![SmartSelect_20220222-153349_Video Player](https://user-images.githubusercontent.com/32845598/155076104-d4e52578-4eba-4025-877c-626df848ade6.gif)


## GATT Server Log 예시
```
2020/11/10 16:37:04 dev: hci0 up
2020/11/10 16:37:04 dev: hci0 reset
2020/11/10 16:37:04 dev: hci0 down
2020/11/10 16:37:04 dev: hci0 opened
State: PoweredOn
2020/11/10 16:37:05 Generating attribute table:
2020/11/10 16:37:05 handle	type	props	secure	pvt	value
...
2020/11/10 16:37:05 Generating attribute table:
2020/11/10 16:37:05 handle	type	props	secure	pvt	value
...
2020/11/10 16:37:05 Generating attribute table:
2020/11/10 16:37:05 handle	type	props	secure	pvt	value
...
2020/11/10 16:37:05 0x0010	0x2800	0x02	0x00	*gatt.Service	[ 9E CA DC 24 0E E5 A9 E0 93 F3 A3 B5 01 00 40 6E ]
2020/11/10 16:37:05 0x0011	0x2803	0x0C	0x00	*gatt.Characteristic	[ 0C 12 00 9E CA DC 24 0E E5 A9 E0 93 F3 A3 B5 02 00 40 6E ]
2020/11/10 16:37:05 0x0012	0x6e400002b5a3f393e0a9e50e24dcca9e	0x0C	0x00	*gatt.Characteristic	[  ]
2020/11/10 16:37:05 0x0013	0x2803	0x30	0x00	*gatt.Characteristic	[ 30 14 00 9E CA DC 24 0E E5 A9 E0 93 F3 A3 B5 03 00 40 6E ]
2020/11/10 16:37:05 0x0014	0x6e400003b5a3f393e0a9e50e24dcca9e	0x30	0x00	*gatt.Characteristic	[  ]
2020/11/10 16:37:05 0x0015	0x2902	0x0E	0x00	*gatt.Descriptor	[ 00 00 ]

Connect:  b4:4b:9b:c7:27:5f
2020/11/10 16:37:09 ignore l2cap signal:[ 06 00 05 00 13 02 02 00 00 00 ]
Disconnect:  b4:4b:9b:c7:27:5f
Connect:  b4:4b:9b:c7:27:5f
2020/11/10 16:37:21 ignore l2cap signal:[ 06 00 05 00 13 02 02 00 00 00 ]
2020/11/10 16:37:29 Send: 1  Length : 4
2020/11/10 16:37:30 Send: 0  Length : 4
2020/11/10 16:37:31 Send: 1  Length : 4
Disconnect:  b4:4b:9b:c7:27:5f
Connect:  b4:4b:9b:c7:27:5f
Disconnect:  b4:4b:9b:c7:27:5f
Connect:  b4:4b:9b:c7:27:5f
2020/11/10 16:37:51 ignore l2cap signal:[ 06 00 05 00 13 02 02 00 00 00 ]
2020/11/10 16:37:55 Send: 1  Length : 4        # indications enabled 상태로 만들어주면 라즈베리파이에서 데이터를 전송하기 시작함
2020/11/10 16:37:56 Send: 0  Length : 4
2020/11/10 16:37:57 Send: 1  Length : 4
2020/11/10 16:37:58 Send: 0  Length : 4
2020/11/10 16:37:59 Send: 1  Length : 4
2020/11/10 16:38:04 Wrote: 12345               # 모바일에서 데이터를 전송하면 라즈베리파이에서 보여짐

```


#### 참고
https://medium.com/fdevtech/bluetooth-low-energy-bluetooth-on-raspberry-pi-3-third-part-521292fe9552
https://punchthrough.com/creating-a-ble-peripheral-with-bluez/
https://learn.adafruit.com/introduction-to-bluetooth-low-energy/gatt
