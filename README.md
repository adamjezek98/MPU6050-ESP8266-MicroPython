# MPU6050-ESP8266-MicroPython
Simple library for MPU6050 on ESP8266 with micropython

SCL connected to pin 5, SDA to pin 4
example usage:

>>>import mpu6050
>>>accelerometer = mpu6050.accel()
>>>accelerometer.get_values()
{'GyZ': -235, 'GyY': 296, 'GyX': 16, 'Tmp': 26.64764, 'AcZ': -1552, 'AcY': -412, 'AcX': 16892}

Accelerometer/Gyroscope valus in int16 range (-32768 to 32767)
If the mpu6050 loses power, yoou have to call __init__() again
