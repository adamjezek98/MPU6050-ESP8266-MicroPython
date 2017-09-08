# MPU6050-ESP8266-MicroPython
Simple library for MPU6050 on ESP8266 with micropython

SCL connected to pin 5, SDA to pin 4
example usage:

```python
>>>from machine import I2C, Pin
>>>import mpu6050
>>>i2c = I2C(scl=Pin(5), sda=Pin(4))
>>>accelerometer = mpu6050.accel(i2c)
>>>accelerometer.get_values()
{'GyZ': -235, 'GyY': 296, 'GyX': 16, 'Tmp': 26.64764, 'AcZ': -1552, 'AcY': -412, 'AcX': 16892}
```
Accelerometer/Gyroscope values are in int16 range (-32768 to 32767)
If the mpu6050 loses power, you have to call __init__() again
