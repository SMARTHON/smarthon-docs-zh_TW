# Case 03: Garbage disposal system 

Level: ![level](images/level2.png)
![auto_fit](images/Case3/case-03.png)<P>


## Goal
<HR>

Make a smart garbage bin by showing different colors of light according to the volume of garbage inside.<BR><P>

## Background
<HR>

<span id="subtitle">What is garbage disposal system?</span><P>
LED light on the garbage bin can show people the amount of garbage inside the garbage bin so that garbage truck can easily determine if the garbage is full or not. This can minimize the wastage of the garbage bags and become a more environmental-friendly city.<BR><P>

<span id="subtitle">Garbage disposal system operation</span><P>
The distance sensor should be able to sense the amount of garbage is inside the garbage bin. Multi-colour LED can be used to emit different colour of light (green and red light), which represent the emptiness of the garbage bin.<BR><P>
![pic_70](images/Case3/Concept-diagram-Case3.png)<P>

## Part List
<HR>

![pic](images/Case3/Case3_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step1</span><P>
Attach the Multi-colour LED to C1 model with M4 screws and nuts.<BR><P>
![pic](images/Case3/Case3_ass1.png)<P>
<span id="subtitle">Step 2</span><P>
Attach the distance sensor to C2 model with M4 screw and nuts.<BR><P>
![pic](images/Case3/Case3_ass2.png)<P>
<span id="subtitle">Step 3</span><P>
Put together all the cardboard parts (C1-C2).<BR><P>
![pic](images/Case3/Case3_ass3.png)<P>
<span id="subtitle">Step 4</span><P>
Assembly completed!<BR><P>
![pic](images/Case3/Case3_ass4.png)<P>

## Hardware connect
<HR>

Connect the Distance Sensor to P14 (trig)/ P15 (echo) port of IoT:bit<BR><P>
Connect Multi-color LED to P1 port of IoT:bit<BR><P>
![pic](images/Case3/Case3_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1</span><P>
Drag on start block from Basic. Set distance to 0 and set strip to NeoPixel at pin P1 with 1 leds as RGB (GRB format).<BR><P>
![pic](images/Case3/Case3_p1.png)<P>
<span id="subtitle">Step 2</span><P>
strip set brightness to 50, pause for 5 seconds for initializing the multi-colour LED.<BR><P>
![pic](images/Case3/Case3_p2.png)<P>
<span id="subtitle">Step 3</span><P>
Drag forever block from Basic. Set distance to get distance unit cm trig P14 echo P15, that’s say get the distance value by connecting the distance sensor to P14 and P15.<BR><P>
![pic](images/Case3/Case3_p3.png)<P>
<span id="subtitle">Step 4</span><P>
Snap if statement into forever, set if distance ≤ 4, then strip show colour red, that’s say the garbage bin is full.<BR><P>
![pic](images/Case3/Case3_p4.png)<P>
<span id="subtitle">Step 5</span><P>
Else, strip show colour green, that’s say the garbage bin is not full.<BR><P>
![pic](images/Case3/Case3_p5.png)<P>
<span id="subtitle">Step 6</span><P>
Pause for 1 seconds from basic.<BR><P>
![pic](images/Case3/Case3_p6.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_HtTDzdT543PV](https://makecode.microbit.org/#pub:_HtTDzdT543PV)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_HtTDzdT543PV" width="100%" height="500" frameborder="0"></iframe>


## Result
<HR>

The distance sensor can return the distance value between the top of the garbage bin and the level of garbage inside the garbage bin. The LED light is used to indicate if the bin is full or not. If it is empty or there are some garbage, the LED turns green, if it is full, the LED turns red.<BR><P>
![pic](images/Case3/Case3_result.gif)<P>

## Think
<HR>

Q1. What other sensor can we use to measure the amount of garbage?<BR><P>
