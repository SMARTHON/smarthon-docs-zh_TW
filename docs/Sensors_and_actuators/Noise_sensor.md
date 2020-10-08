# Noise Sensor

![pic_50](images/Noise_Sensor_0.png)
## Introduction
Noise sensor use a microphone with an amplifier to detect the sound level of the environment. It will capture the original sound wave, enlarge, and reproduce it in voltage form. When using the sensor to calculate the sound level, use the amplitude to decide the result.
<P>


## The principle
The Noise Sensor is a combine of the microphone and amplifier, the microphone will capture the raw signal form the environment and let the amplifier chip lm386 to produce the amplified signal to the output. <P>
![auto_fit](images/Noise_Sensor_1.png)


## Specification 
* Supply voltage: 3.3V – 5V
* Interface: Analog
* Output Range: 0~3.5V
 
Voltage when silent: (1.74~1.83V)<BR>
![auto_fit](images/Noise_Sensor_2.png) <P>
Voltage Under 440Hz sound:(0.98 ~ 2.58V)
![auto_fit](images/Noise_Sensor_3.png) <P>

## Pinout Diagram

|Pin|Function|
|--|--|
|G|Ground|
|V|Voltage Supply|
|S|Voltage Signal Output|

## Outlook and Dimension
![pic_70](images/Noise_Sensor_4.png)

Size: 25mm X 25mm

## Quick to Start/Sample

* Connect the sensor to development board (using wire)
![auto_fit](images/Noise_Sensor_5.png)<P>

* Open Makecode, using the https://github.com/smarthon/pxt-smartcity PXT <P>
![auto_fit](images/Noise_Sensor_6.png)<P>

* Initial the OLED screen and show the reading of the noise level.
![auto_fit](images/Noise_Sensor_7.png)

## Result

When the environment is quite silent without noise
![pic_70](images/Noise_Sensor_8.png)

When people speak louder 
![pic_70](images/Noise_Sensor_9.png)

## FAQ

Q:Why the value of sensor is stay in the silent level?<BR>
A: Try to adjust the sensitive level by the regulator, it is locate on the board, use a screwdriver can turning it easily.



## Datasheet

[LM386-datasheet](https://www.ti.com/lit/ds/symlink/lm386.pdf)
