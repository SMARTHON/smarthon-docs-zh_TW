# Case 02: Smart Car park Access Barrier

Level: ![level](images/level2.png)
![auto_fit](images/Case2/case-02.png)<P>

## Goal
<HR>

Make a smart car park gate which opens automatically if there are vacancies in the car park and there are cars coming in.<BR><P>

## Background
<HR>

<span id="subtitle">What is smart car park access barrier?</span><P>
Smart Car park Access Barrier is used to allow people to live conveniently. It can reduce manpower and time in controlling the gate and manage information (e.g. car park vacancies). It will be opened automatically if there are vacancies in the car park and there are cars coming in.<BR><P>

<span id="subtitle">Car park gate operation</span><P>
The car park gate open and close operation is controlled by 180ᵒ servo. It will be opened if there are vacancies in the car park (i.e. detected by light sensor) and cars near the car park gate (i.e. detected by distance sensor). Otherwise, the gate will be closed.<BR><P>
When there are no vacancies (detected by light sensor), then the gate will keep closed.<BR><P>
![pic_70](images/Case2/Concept-diagram-Case2.png)<P>


## Part List
<HR>

![auto_fit](images/Case2/Case2_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step 1</span><BR><P>
Attach the distance sensor to B1 model with M4 * 10mm screws and nuts. <BR><P>
![auto_fit](images/Case2/Case2_ass1.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Attach the servo to B1 model with M2 * 10mm screws and nuts<BR><P>
![auto_fit](images/Case2/Case2_ass2.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Attach the B2 model to the servo with servo M2 * 7.5mm sharp screw. Put B3 model onto B1 model.<BR><P>
![auto_fit](images/Case2/Case2_ass3.png)<P>
<span id="subtitle">Step 4</span><BR><P>
Assembly completed! <BR><P>
![pic_60](images/Case2/Case2_ass4.png)<P>


## Hardware connect
<HR>

Connect the Distance Sensor to P14 (trig)/ P15 (echo) port of IoT:bit<BR><P>
Connect Light Sensor to P0 port of IoT:bit<BR><P>
Connect 180° Servo to P2 port of IoT:bit<BR><P>
![auto_fit](images/Case2/Case2_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Set variables and servo at start position</span><BR><P>
* Inside `on start`, snap `set variable distance to 0` and `set light to 0` from `variables`. Snap `Turn Servo to 0 degree at P2`.
![pic_50](images/Case2/Case2_p1.png)<P>

<span id="subtitle">Step 2. Get distance and light value</span><BR><P>
* Drag `get distance to get distance unit cm trig P14 echo P15`, store the value to variable `distance`.
* `Get light value (percentage) at Pin P0`, store the value to variable `light`
![pic_90](images/Case2/Case2_p2.png)<P>

<span id="subtitle">Step 3. Open/close gate with light value</span><BR><P>
* Snap `if statement` into forever, set if variable `distance` ≤ 5
* Snap another `if statement` set variable `light` value >20
![pic_90](images/Case2/Case2_p3.png)<P>

<span id="subtitle">Step 4. Set servo position</span><BR><P>
* Snap `Turn Servo to 90 degree at P2` as the gate is opened.
* Snap `pause` to the loop to wait 5 seconds
* Snap `Turn Servo to 0 degree at P2` as the gate is closed.
![pic_90](images/Case2/Case2_p4.png)<P>



<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_V1hdbVYzwCeD](https://makecode.microbit.org/#pub:_V1hdbVYzwCeD)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_V1hdbVYzwCeD" width="100%" height="500" frameborder="0"></iframe>

## Result
<HR>

The light sensor is used to check the vacancies in the car park while the distance sensor is used to detect if there are any cars coming near the car park gate<BR><P>
The car park gate is controlled by 180ᵒ servo. When there are vacancies in the car park and there are cars near the car park gate, the car park is available. The gate will be opened for 5 seconds and then closed to let the car entering the car park.<BR><P>
![auto_fit](images/Case2/Case2_result.gif)<P>

## Think
<HR>

Q1. How can you show the light and distance value on OLED?<BR><P>
Q2. Can you show signals on micro:bit LED to let drivers know there are vacancies in the car park?<BR><P>
