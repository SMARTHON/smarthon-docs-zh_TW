# Ultrasonic Distance Sensor US-025A

![pic_70](images/Ultrasonic_Distance_Sensor_0.jpg)
## Introduction
The Distance sensor using two ultrasonic sensors to detect the distance between current position and object. In most situation, the availability of ultrasonic allow it provided quick and accurate result.
<P>


## The principle
The Distance sensor use the ultrasonic to measure the distance between the sensor and object. When the sensor emit a wave of ultrasonic wave, it will start passing thought the air until it hit the object, then rebound and back to the receiver. The sound wave travel in the air is approximately 340meter per second, with it, use the interval time between sent and received can calculate the distance. <P>
![auto_fit](images/Ultrasonic_Distance_Sensor_1.png)


## Specification 
* Supply voltage: 5V
* Working Frequency: 40kHz
* Range: 3cm to 4m 
* MeasuringAngle: <15°

## Pinout Diagram

|Pin|Function|
|--|--|
|GND|Ground|
|VCC|Voltage Supply|
|Trig|Starting trigger signal Input|
|Echo|Response signal Output|

## Outlook and Dimension
![pic_70](images/Ultrasonic_Distance_Sensor_2.png)

Size: 41 X 25mm

## Quick to Start/Sample

* Connect the sensor to development board (using wire)
![auto_fit](images/Ultrasonic_Distance_Sensor_3.png)<P>

* Open Makecode, using the https://github.com/smarthon/pxt-smartcity PXT <P>
![auto_fit](images/Ultrasonic_Distance_Sensor_4.png)<P>

* Initial the OLED and show the distance value on the OLED screen
![auto_fit](images/Ultrasonic_Distance_Sensor_5.png)

## Result

The Distance will be increasing when moving out the hand from sensor
![pic_70](images/Ultrasonic_Distance_Sensor_6.png)


## FAQ

Q: Why I cannot get the correct reading in far distance?<BR>
A: Because of the ultrasonic sender and receiver both on the board, limited by the physical reason, the reflection angle of the object will affect the result correctly, especially when the distance is far, little reflection angle can create large displacement of mainstream, so please adjust the angle of detection.

