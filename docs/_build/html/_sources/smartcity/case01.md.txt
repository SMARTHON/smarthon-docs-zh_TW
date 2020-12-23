# Case 01: Automated Smart Playground Lamp

Level: ![level](images/level1.png)
![auto_fit](images/Case1/case-01_1.png)<P>


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

![pic_60](images/Case1/Concept-diagram-Case1.png)<P>

## Part List
<HR>

![auto_fit](images/Case1/Case1_parts.png)<P>


## Assembly step
<HR>

<span id="subtitle">Step 1</span><BR><P>
Attach motion sensor and white LED to A1 model with M4 * 10mm screws and nuts.<BR><P>
![auto_fit](images/Case1/Case1_ass1.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Assembly completed!<BR><P>
![pic_40](images/Case1/Case1_ass2.png)<P>


## Hardware connect
<HR>

Connect Motion sensor to the P0 port of Smarthon IoT:bit<BR><P>
Connect LED light to the P3 port of Smarthon IoT:bit<BR><P>
<BR>![auto_fit](images/Case1/Case1_hardware.png)
<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Disable micro:bit LED.</span><BR><P>
* Snap `led enable false` to `on start` 
* Note that P3 is used as LED in default setting, LED need to be disable 
![auto_fit](images/Case1/Case1_p1.png)<P>

<span id="subtitle">Step 2. Turn on LED by motion sensor</span><BR><P> 
* Drag `forever` from `Basic`
* Snap `if statement` into `forever`
* Set `get motion (triggered or not) at P0 = true`, into `if statement` that’s say motion is triggered, someone passes by. 
* Then, `turn white LED to 1023 at P3` as turning on white LED and pause 10 seconds. 
* Else, `turn white LED at P3 to 0` as turning off.
![pic_90](images/Case1/Case1_p2.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_PVf42KbHx0zY](https://makecode.microbit.org/#pub:_PVf42KbHx0zY_5jAUk558DTXC)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_PVf42KbHx0zY" width="100%" height="500" frameborder="0"></iframe>

<P>

## Result
<HR>

Motion sensor is used to detect if there are people moving in the playground. If there are, the LED light will be turned on; otherwise, it will be turned off.<BR><P>
![auto_fit](images/Case1/Case1_result.gif)<P>

## Think
<HR> 

Q1. How can you use motion sensors, other than turning  on the light automatically?<BR><P>

<!---
Q2. How should we reset the programming if we connect the white LED light to P3?<BR><P>
Tips: As P3 is used by micro:bit LED. 
(Refer to [https://makecode.microbit.org/device/pins](https://makecode.microbit.org/device/pins))<BR>
If we connect white LED light to P3, we need to disable micrbo:bit LED.<BR><P>
![auto_fit](images/Case1/Case1_think.png)<P>
-->

Q2. Can you show motion sensor value on OLED?<P>
