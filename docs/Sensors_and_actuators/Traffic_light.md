# Traffic Light

![pic_70](images/Traffic_Light_0.jpg)
## Introduction
The traffic light module including three different colors LED which are red, yellow and green color, like the real-life traffic light. When received different frequency of PWM signal, it will provide different pattern of light.
<P>


## The principle
![auto_fit](images/Traffic_Light_1.png)
Most of the traffic light module on market will using the concept of common anode to make it easy to use. However, it required 4 pin on the module(3 signal and 1 ground) and consume 3 control pin from the controller, make it become heavy and hard to use on some tiny device.<BR>When using PWM method instead of common anode, it can reduce to 3pins and only consume 1 signal pin form the controller, more suitable for the tiny project.<P>
![pic_70](images/Traffic_Light_2.png)

The PWM signal can represent in the average voltage output, or duty cycle % in one complete cycle. This module will control by the duty cycle method.<BR>The chip on the traffic light module keep recording the incoming PWM signal and distinguish the “states” of traffic light by the preset duty cycle % level table. Then control the turn on /off states of the three LED lights.<P>

## Specification 
* Supply voltage: 3.3V~5V
* Interface: Analog/Digital PWM

Duty Cycle:<BR>

|Duty cycle(%)|Light|
|--|--|
|<5|OFF: Red Yellow Green|
|5~12.5|ON: Green<BR>OFF: Red Yellow|
|12.5~25|ON: Yellow<BR>OFF: Red Green|
|25~37.5|ON: Yellow Green<BR>OFF: Red|
|37.5~50|ON: Red<BR>OFF: Yellow Green|
|50~62.5|ON: Red Green<BR>OFF: Yellow|
|62.5~75|ON: Red Yellow<BR>OFF: Green|
|>75|ON: Red Yellow Green|

## Pinout Diagram

|Pin|Function|
|--|--|
|G|Ground|
|V|Voltage Supply|
|S|Signal Input (PWM Voltage)|

## Outlook and Dimension
![pic_70](images/Traffic_Light_3.png)

Size: 25mm X 45mm

## Quick to Start/Sample

* Connect the sensor to development board (using wire)
![auto_fit](images/Traffic_Light_4.png)<P>

* Open Makecode, using the https://github.com/smarthon/pxt-smartcity PXT <P>
![auto_fit](images/Traffic_Light_5.png)<P>

* Provide the corresponding PWM signal
![auto_fit](images/Traffic_Light_6.png)

## Result
The traffic light will turn on and off
![pic_70](images/Traffic_Light_7.gif)

## FAQ

Q: Why the lights is out of control?<BR>
A: Check the PWM signal duty cycle is fit the requirement or not. Also be care the change of light status should not too quick, at least wait for 1 second.



