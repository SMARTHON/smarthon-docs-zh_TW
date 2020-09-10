# Case 01: Automated Smart Playground Lamp

Level: ![level](images/level1.png)

## Goal
<HR>
Make a smart playground lamp by detecting the motion nearby.<P>

## Background
<HR>
<B>What is smart playground lamp?</B><P>

Smart playground lamp is a lamp which can open automatically when someone passes by. Installing an
auto-light can help the earth save electricity. When no one passes by, the light will automatically turn off.<P>

<B>Smart playground lamp operation</B><P>

Motion sensor should be able to detect if there are people moving in the playground.<BR>
If there are people moving in the playground, the LED light should turn on, vice versa.<BR>

## Part List: 
<HR>
<table><tr><td>
Electronics:
<ul display='inline-block'>
<li>micro:bit X1</li>
<li>Smarthon IoT:bit X1</li>
<li>USB Wire/Battery Holder X1</li>
&nbsp;&nbsp;1. White LED Light X1(With Module Wire)<BR>
&nbsp;&nbsp;2. Motion Sensor X1 (With Module Wire)
</ul>
</td></tr>
<tr>
<td>Model:
<ul>
<li>Playground Lamp Cardboard Model A1-A3 X1</li>
<li>M4 Screw X2</li>
<li>M4 Nuts X2</li>
</ul>
</td></tr>
<tr><td>Equipment:
<ul><li>ScrewDriver X1</li></ul></td></tr></table>

![auto_fit](images/Case1_01.png)
<P>

## Practical Operation
<HR>

1. Screw the sensor<BR>Attach the LED light to the model . Attach motion sensor to A1 model with M4 screws and nuts.<BR>
![auto_fit](images/Case1_02.png)<P>
2. Attach the white LED light to A3 model with M4 screws and nuts.<BR>
![auto_fit](images/Case1_03.png)<BR>
3. Put together all the cardboard parts (A1-A3)<BR>
![auto_fit](images/Case1_04.png)

## Hardware connect
<HR>

* Connect Motion sensor to the P0 port of Smarthon IoT:bit
* Connect LED light to the P1 port of Smarthon IoT:bit
<BR>![auto_fit](images/Case1_05.png)
<P>

## Programming:
<HR>

Step1. Drag forever block from Basic. Snap if statement into forever, set get motion (triggered or not) at P0=true, that's say motion is triggered, someone passes by.<BR>
![auto_fit](images/Case1_06.png)
Step2. Turn white LED to 1023 at P1 as turning on white LED and pause 10 seconds.
![auto_fit](images/Case1_07.png)
Step3. Else, turn white LED to 0 at P1 as turing off white LED.
![auto_fit](images/Case1_08.png)
<P>

[https://makecode.microbit.org/v2/#pub:_44zg2oKFRLhs](https://makecode.microbit.org/v2/#pub:_44zg2oKFRLhs)<BR>
<iframe src="https://makecode.microbit.org/v2/#pub:_44zg2oKFRLhs" width="100%" height="500" frameborder="0"></iframe>

<P>

## Result:
<HR>

![auto_fit](images/Case1_09.gif)
Motion sensor is used to detect if there are people moving in the playground. If there are, the LED light will be turned on; otherwise, it will be turned off.

## Think
<HR> 

Q1. How can you use motion sensors, other than turning  on the light automatically?<BR>
Q2. How should we reset the programming if we connect the white LED light to P3?<BR>
Tips: We need to disable LED to use Pin P3.
![auto_fit](images/Case1_10.png)
(Refer to [Micro:bit](https://makecode.microbit.org/device/pins))	
<BR>Q3. Show motion sensor value on OLED
