This are observations of a Nao v6 robot, visiting the locations defined in the 2004 SLAM challenge.

Every point contains:
- A picture of the top camera
- A picture of the bottom camera
- Optitrack data of the few seconds in which the picture is taken. The last few seconds are more likely to be the actual position than the first or in the middle. This is due to the blocking of the sensors when I pressed their feet.
- A 'record' csv, containing the following data, in order:
    "Device/SubDeviceList/HeadPitch/Position/Actuator/Value"
    "Device/SubDeviceList/HeadPitch/Position/Sensor/Value"
    "Device/SubDeviceList/HeadYaw/Position/Actuator/Value"
    "Device/SubDeviceList/HeadYaw/Position/Sensor/Value"
    "Device/SubDeviceList/InertialSensor/GyroscopeX/Sensor/Value"
    "Device/SubDeviceList/InertialSensor/GyroscopeY/Sensor/Value"
    "Device/SubDeviceList/InertialSensor/GyroscopeZ/Sensor/Value"
    "Device/SubDeviceList/InertialSensor/AngleX/Sensor/Value"
    "Device/SubDeviceList/InertialSensor/AngleY/Sensor/Value"
    "Device/SubDeviceList/InertialSensor/AngleZ/Sensor/Value"
    "Device/SubDeviceList/InertialSensor/AccelerometerX/Sensor/Value"
    "Device/SubDeviceList/InertialSensor/AccelerometerY/Sensor/Value"
    "Device/SubDeviceList/InertialSensor/AccelerometerZ/Sensor/Value"
    What each value means and what the measurements are (cm, rads, etc) can be found here: http://doc.aldebaran.com/2-8/family/nao_technical/lola/actuator_sensor_names.html
