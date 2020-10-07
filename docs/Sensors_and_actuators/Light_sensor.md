# Light Sensor

![pic_50](images/Light_Sensor_0.png)
## Introduction
The Light sensor use one photoresistor to detect the luminance of environment. The darker of the environment, the lower voltage will be provided. 
<P>


## The principle
The Light sensor also call as Light Dependent Resistor(LDR), the physical property will change under different light source as the name implied.  <P>
![auto_fit](images/Light_Sensor_1.png)

Depend on the model of different LDR, the resistance value and curves have difference, but all follow the principle: <BR>
When the Illumination is increase, the resistance of the resistor will reduce.<BR>
When the Illumination is decrease, the resistance of resistor will increase. <BR>


## Specification 
* Supply Voltage: 3.3V to 5V
* Interface: Analog 
* Output Voltage Range: 1%~90% of supply Voltage
* Reading in the PXT(with Mirco:bit): 1~100(0.04V~3.3V)


## Pinout Diagram

|Pin|Function|
|--|--|
|G|Ground|
|V|Voltage Supply|
|S|Signal Output(Analog)|

## Outlook and Dimension
![pic_60](images/Light_Sensor_2.png)

Size: 25mm X 25mm

## Quick to Start/Sample

* Connect the sensor to development board (direct plugin or using wire))
![auto_fit](images/Light_Sensor_3.png)<P>

* Open Makecode, using the https://github.com/smarthon/pxt-smartcity PXT <P>
![auto_fit](images/Light_Sensor_4.png)<P>

* Initial the OLED and show the reading of Voltage Output
![auto_fit](images/Light_Sensor_5.png)

## Result

The reading of the luminance will show according to the environment. 
![pic_60](images/Light_Sensor_6.png)

## FAQ

Q: Why the reading mostly stays in the middle range?<BR>
A: Generally, using in a in-door environment (with electric light source) will have a middle range value.<BR>
The close to limit value will only appear in the extreme cases, like under the sun/ close to light bulb, or stay in a full dark environment.


## Datasheet

[Photoresistor-5516-datasheet](http://yourduino.com/docs/Photoresistor-5516-datasheet.pdf)
