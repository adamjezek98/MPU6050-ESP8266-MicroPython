# MPU6050-ESP8266-MicroPython
Simple library for MPU6050 on ESP8266 with micropython

SCL connected to pin 5, SDA to pin 4
example usage:

```python
>>>from machine import I2C, Pin
>>>import mpu6050
>>>i2c = I2C(scl=Pin(5), sda=Pin(4))
>>>imu = mpu6050.accel(i2c)
>>> imu.get_values()
{'GyZ': -60, 'GyY': -68, 'GyX': 2, 'Tmp': 33.04765, 'AcZ': 16048, 'AcY': 44, 'AcX': -952}
>>> imu.sleep()
>>> imu.get_values()
{'GyZ': -38, 'GyY': 56, 'GyX': -38, 'Tmp': 33.00059, 'AcZ': 15824, 'AcY': -40, 'AcX': -708}
>>> imu.get_values()
{'GyZ': -38, 'GyY': 56, 'GyX': -38, 'Tmp': 33.00059, 'AcZ': 15824, 'AcY': -40, 'AcX': -708}
>>> imu.wakeup()
>>> imu.get_values()
{'GyZ': -28, 'GyY': 59, 'GyX': -44, 'Tmp': 32.85941, 'AcZ': 15948, 'AcY': -76, 'AcX': -852}
```
Accelerometer/Gyroscope values are in int16 range (-32768 to 32767)
If the mpu6050 loses power, you have to call __init__() again

Source: https://github.com/adamjezek98/MPU6050-ESP8266-MicroPython

