# BLEPeripheral-RPI
Using a RaspberryPI as a BLE peripheral

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


#### 참고
https://medium.com/fdevtech/bluetooth-low-energy-bluetooth-on-raspberry-pi-3-third-part-521292fe9552
https://punchthrough.com/creating-a-ble-peripheral-with-bluez/
https://learn.adafruit.com/introduction-to-bluetooth-low-energy/gatt
