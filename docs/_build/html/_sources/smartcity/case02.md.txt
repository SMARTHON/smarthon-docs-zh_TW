# Case 02: Smart Car park Access Barrier

![pic](images/Case2_01.png)
Level: ![level](images/level2.png)

## Goal
<HR>

Make a smart car park gate which opens automatically if there are vacancies in the car park and there are cars coming in.<BR><P>

## Background
<HR>

<span id="subtitle">What is smart car park access barrier?</span><P>
Smart Car park Access Barrier is used to allow people to live conveniently. It can reduce manpower and time in controlling the gate and manage information (e.g. car park vacancies). It will be opened automatically if there are vacancies in the car park and there are cars coming in.<BR><P>

<span id="subtitle">Car park gate operation</span><P>
The car park gate open and close operation is controlled by 180ᵒ servo. It will be opened if there are vacancies in the car park (i.e. detected by light sensor) and cars near the car park gate (i.e. detected by distance sensor). Otherwise, the gate will be closed.<BR><P>

## Part List
<HR>

Electronics:
* micro:bit X1
* Smarthon IoT:bit X1
* OLED X1
* USB Wire/Battery Holder
* Light Sensor X1 (With Module wire)
* Distance Sensor X1 (With Module wire)
* 180° Servo X1

Model:
* Distance Sensor Stand Model D1-D3 X1
* M4 Screws X4
* M4 Nuts X4
* M2 Screw X2
* M2 Nuts X2

Equipment:
* ScrewDriver X1

## Practical operation
<HR>

Screw the sensor (Paste photos here later)
* Attach the distance sensor to the stand model (D1)
* Screw the car park gate (D2) onto the stand model (D1)

Build the model 
* Put together all the cardboard parts D1-D3

## Hardware connect
<HR>

Connect the Distance Sensor to P14 (trig)/ P15 (echo) port of IoT:bit<BR><P>
Connect Light Sensor to P0 port of IoT:bit<BR><P>
Connect 180° Servo to P2 port of IoT:bit<BR><P>
![pic](images/Case2/Case2_hardware.png)<P>

## Programming
<HR>

<span id="subtitle">Step 1</span><BR><P>
Drag on start block from Basic. Set distance and light to 0 from variables and turn servo to 0 degree at P2 at the beginning.<BR><P>
![pic](images/Case2/Case2_p1.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Drag forever block from Basic. Set distance to get distance unit cm trig P14 echo P15. set light to get light value (percentage) at Pin P0.<BR><P>
![pic](images/Case2/Case2_p2.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Snap if statement into forever, set if distance ≤ 5. Snap another if and set light value >50 then, <BR><P>
![pic](images/Case2/Case2_p3.png)<P>
<span id="subtitle">Step 4</span><BR><P>
After measuring the distance and light, turn servo to 90 degree at P2, pause 5 seconds and turn servo to 0 degree at P2. <BR><P>
That’s say when there is car entering and there is vacancy inside the car park, the car park gate will be opened for 5 seconds for car entering.<BR><P>
![pic](images/Case2/Case2_p4.png)<P>

## Result
<HR>

The light sensor is used to check the vacancies in the car park while the distance sensor is used to detect if there are any cars coming near the car park gate<BR><P>
The car park gate is controlled by 180ᵒ servo. When there are vacancies in the car park and there are cars near the car park gate, the car park is available. The gate will be opened for 5 seconds and then closed to let the car entering the car park.<BR><P>


## Think
<HR>

Q1. How can you show the light and distance value on OLED?<BR><P>
![pic](images/Case2/Case2_think.png)<P>
Q2. Can you show signals on micro:bit LED to let drivers know there are vacancies in the car park?<BR><P>

