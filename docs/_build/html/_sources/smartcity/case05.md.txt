# Case 05: Car speed monitoring 

Level: ![level](images/level3.png)

## Goal
<HR>

Make a car speed monitor to detect car speed on the road.<BR><P>

## Background
<HR>

<span id="subtitle">What is car speed monitoring?</span><P>
It is an automatic system to check car speed on the road at certain time interval. There are cars often over-speed causing traffic accidents, therefore installing a car speed monitoring is a must to minimize the chances of traffic accidents.<BR><P>

<span id="subtitle">Car speed monitor operation</span><P>
The distance sensor measures two different distances at certain time interval, and therefore car speed can be calculated and shows it on the OLED. <BR><P>
On every 500ms (0.5 second), the distance sensor will keep updating distance between the sensor and the car. <BR><P>
![auto_fit](images/Case5/Case5_des1.png)<P>
If distance 1 ≥ distance 2, that’s say the car is moving towards. The moving distance is distance1 -distance2. The speed is (distance1-distance2)/0.5 (unit: cm/s) <BR><P>
If distance 1 = distance 2, that’s say the car has stop moving or there are no cars. The moving distance and speed are 0 <BR><P>
For car speed < 0, it is the exceptional case (the car turns left/right and leave the road) and the speed will not be shown. <BR><P>
A bar graph on micro:bit LED is shown to indicate the instant speed of the cars. <BR><P>
![auto_fit](images/Case5/Case5_des2.png)<P>

## Part List
<HR>

<table><tr><td>
Electronics:
<ul display='inline-block'>
<li>micro:bit (with OLED) X1</li>
<li>IoT:bit X1</li>
<li>OLED extension wire X1</li>
<li>USB Wire/Battery Holder </li>
&nbsp;&nbsp;1. Distance Sensor X1 (wWith 4-pin mModule wire) <BR>
</ul>
</td></tr>
<tr>
<td>Model:
<ul>
<li>Car speed monitoring stand Model E1-E2 X1</li>
<li>Car speed showing stand Model D1-D2 X1</li>
<li>M4 Screws X4</li>
<li>M4 Nuts X4</li>
<li>M2 Screws X4</li>
<li>M2 Nuts X4</li>
</ul>
</td></tr>
<tr><td>Equipment:
<ul><li>ScrewDriver X1</li></ul></td></tr></table>

![auto_fit](images/Case5/Case5_parts.png)<P>

## Practical operation
<HR>

<span id="subtitle">Step 1</span><P>
Attach the OLED to D1 model using M2 x10mm screw and nut.<BR><P>
![auto_fit](images/Case5/Case5_po1.png)<P>
<span id="subtitle">Step 2</span><P>
Put D2 model onto the D1 model.<BR><P>
![auto_fit](images/Case5/Case5_po2.png)<P>
<span id="subtitle">Step 3</span><P>
Attach the distance sensor to E1 model using M4 screw and nut.<BR><P>
![auto_fit](images/Case5/Case5_po3.png)<P>
<span id="subtitle">Step 4</span><P>
Put the E2 model onto E1 model.<BR><P>
![auto_fit](images/Case5/Case5_po4.png)<P>


## Hardware connect
<HR>

Connect the Distance Sensor to P14 (trig)/ P15 (echo) port of IoT:bit <BR><P>
Extend the connection of OLED to the I2C connection port of IoT:bit <BR><P>
![auto_fit](images/Case5/Case5_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1</span><P>
Drag on start block from Basic. Drag Initialize IoT:bit at OLED from IoT:bit, set OLED height:64, width:128.<BR><P>
![auto_fit](images/Case5/Case5_p1.png)<P>
<span id="subtitle">Step 2</span><P>
Set distance 1, distance 2 and speed to 0 from variables. <BR><P>
 ![auto_fit](images/Case5/Case5_p2.png)<P>
<span id="subtitle">Step 3</span><P>
Set up a new function (calculate_Speed). Set distance1 to get distance unit cm trig P14 echo P15 (distance from the car to the distance sensor before 0.5 second)<BR><P>
![auto_fit](images/Case5/Case5_p3.png)<P>
<span id="subtitle">Step 4</span><P>
Pause 500ms and get distance2 to get distance unit cm trig P14 echo P15 (distance from the car to the distance sensor after 0.5 second)<BR><P>
 ![auto_fit](images/Case5/Case5_p4.png)<P>
<span id="subtitle">Step 5</span><P>
By the equation of speed = distance / time. We get the speed of the moving car to (distance1-distance2)/0.5 (unit: cm/s)<BR><P>
 ![auto_fit](images/Case5/Case5_p5.png)<P>
<span id="subtitle">Step 6</span><P>
Drag forever block from Basic. Call function (calculate_Speed) to get the speed of the moving car.<BR><P>
 ![auto_fit](images/Case5/Case5_p6.png)<P>
<span id="subtitle">Step 7</span><P>
If the speed ≥0, then OLED will show the distance1, distance2 and speed.<BR><P>
 ![auto_fit](images/Case5/Case5_p7.png)<P>
<span id="subtitle">Step 8</span><P>
Plot bar graph of speed up to 20 from LED, which means showing a bar graph on Micro:bit based on the recorded speed.<BR><P>
![auto_fit](images/Case5/Case5_p8.png)<P>

## Results
<HR>

It will keep checking the distance of cars from distance sensor by distance sensor in every 500ms. The speed of the cars will be shown on OLED. A bar chart of speed will be shown on micro:bit LED also.<BR><P>
<span id="subtitle">Car moving with low speed</span><P>
![auto_fit](images/Case5/Case5_result1.gif)<P>
<span id="subtitle">Car moving with high speed</span><P>
![auto_fit](images/Case5/Case5_result2.gif)<P>

## Think
<HR>

How can we set a sound alert to notify that there is car over-speeding?<BR><P>

