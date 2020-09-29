# Case 01: Automated Smart Playground Lamp

Level: ![level](images/level1.png)

![auto_fit](images/Case1/concept-2.4.png)<P>


## Goal
<HR>
Make a smart playground lamp by detecting the motion nearby.<P>

## Background
<HR>
<span id="subtitle">What is smart playground lamp?</span><P>

Smart playground lamp is a lamp which can open automatically when someone passes by. Installing an
auto-light can help the earth save electricity. When no one passes by, the light will automatically turn off.<P>

<span id="subtitle">Smart playground lamp operation</span><P>

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
&nbsp;&nbsp;1. White LED Light X1(With 3-pin module wire)<BR>
&nbsp;&nbsp;2. Motion Sensor X1 (With 3-pin module wire)
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

![auto_fit](images/Case1/Case1_parts.png)<P>


## Practical Operation 1
<HR>

<span id="subtitle">Assembly Instructions Document</span><BR><P>
Automated Smart Playground Lamp: [Download](https://raw.githubusercontent.com/SMARTHON/smarthon-docs-en/master/docs/smartcity/files/Case1e.jpg)<P>

<span id="subtitle">Assembly Instructions (Model A1-A3)</span><BR><P>
Part list: ![auto_fit](files/Case1_b.png)<P>

Steps: <BR>
1. Attach motion sensor to A1 model with M4 screws and nuts.<BR><P>
2. Attach the white LED light to A2 model with M4 screws and nuts.<BR><P>
![auto_fit](files/Case1_a1.png)<P>
3. Assembly complete!<BR><P>
![auto_fit](files/Case1_a2.png)<P>


## Practical Operation 2
<HR>

<span id="subtitle">Steps</span><BR><P>
1. Attach motion sensor to A1 model with M4 screws and nuts.<BR><P>
2. Attach the white LED light to A2 model with M4 screws and nuts.<BR><P>
3. Put together all the cardboard parts (A1-A3)<BR><P>
![auto_fit](files/Case1e_2.png)<P>


## Practical Operation 3
<HR>

<span id="subtitle">Step 1</span><BR><P>
Attach motion sensor to A1 model with M4 screws and nuts.<BR><P>
![auto_fit](images/Case1/Case1_op1.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Attach the white LED light to A2 model with M4 screws and nuts.<BR><P>
![auto_fit](images/Case1/Case1_op2.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Put together all the cardboard parts (A1-A3)<BR><P>
![auto_fit](images/Case1/Case1_op3.png)<P>


## Hardware connect
<HR>

Connect Motion sensor to the P0 port of Smarthon IoT:bit<BR><P>
Connect LED light to the P1 port of Smarthon IoT:bit<BR><P>
<BR>![auto_fit](images/Case1/Case1_hardware.png)
<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1</span><BR><P>
Drag forever block from Basic. Snap if statement into forever, set get motion (triggered or not) at P0=true, that's say motion is triggered, someone passes by.<BR><P>
![auto_fit](images/Case1/Case1_p1.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Turn white LED to 1023 at P1 as turning on white LED and pause 10 seconds.<P>
![auto_fit](images/Case1/Case1_p2.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Else, turn white LED to 0 at P1 as turing off white LED.<P>
![auto_fit](images/Case1/Case1_p3.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_P36fA38jVih2](https://makecode.microbit.org/#pub:_P36fA38jVih2)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_P36fA38jVih2" width="100%" height="500" frameborder="0"></iframe>

<P>

## Result
<HR>

Motion sensor is used to detect if there are people moving in the playground. If there are, the LED light will be turned on; otherwise, it will be turned off.<BR><P>
![auto_fit](images/Case1/Case1_result.gif)<P>

## Think
<HR> 

Q1. How can you use motion sensors, other than turning  on the light automatically?<BR><P>
Q2. How should we reset the programming if we connect the white LED light to P3?<BR><P>
Tips: As P3 is used by micro:bit LED. 
(Refer to [https://makecode.microbit.org/device/pins](https://makecode.microbit.org/device/pins))<BR>
If we connect white LED light to P3, we need to disable micrbo:bit LED.<BR><P>
![auto_fit](images/Case1/Case1_think.png)<P>
	
Q3. Show motion sensor value on OLED<P>
