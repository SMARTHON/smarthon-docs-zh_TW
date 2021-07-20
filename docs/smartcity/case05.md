# Case 05: Car speed monitoring 

Level: ![level](images/level3.png)
![auto_fit](images/Case5/case-05.png)<P>

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

![pic_70](images/Case5/Concept-diagram-Case5.png)<P>
## Part List
<HR>

![auto_fit](images/Case5/Case5_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step 1</span><P>
Attach the OLED to D1 model using M2 * 10mm screw and nut.<BR><P>
![auto_fit](images/Case5/Case5_ass1.png)<P>
<span id="subtitle">Step 2</span><P>
Put D2 model onto the D1 model.<BR><P>
![auto_fit](images/Case5/Case5_ass2.png)<P>
<span id="subtitle">Step 3</span><P>
Assembly completed!
![pic_40](images/Case5/Case5_ass3.png)<P>
<span id="subtitle">Step 4</span><P>
Attach the distance sensor to E1 model using M4 screw and nut.<BR><P>
![auto_fit](images/Case5/Case5_ass4.png)<P>
<span id="subtitle">Step 5</span><P>
Put the E2 model onto E1 model.<BR><P>
![auto_fit](images/Case5/Case5_ass5.png)<P>
<span id="subtitle">Step 6</span><P>
Assembly completed!<BR><P>
![pic_40](images/Case5/Case5_ass6.png)<P>

## Hardware connect
<HR>

Connect the Distance Sensor to P14 (trig)/ P15 (echo) port of IoT:bit <BR><P>
Extend the connection of OLED to the I2C connection port of IoT:bit <BR><P>
![auto_fit](images/Case5/Case5_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize OLED screen</span><P>
* Drag `Initialize OLED with width:128, height: 64` to `on start`
* Set `distance1`, `distance2` and `speed` to 0 from `variables`
![auto_fit](images/Case5/Case5_p1.png)<P>

<span id="subtitle">Step 2. Set up function (calculate_Speed)</span><P>
* Set up a new function `calculate_Speed` from `Advanced` > `Functions`. 
* Set `distance1` to `get distance unit cm trig P14 echo P15` (distance from the car to the distance sensor before 0.5 second)
Drag `Pause` to wait 500ms and set `distance2` to `get distance unit cm trig P14 echo P15` (distance from the car to the distance sensor after 0.5 second)
* By the equation of speed = distance / time. We get the `speed` of the moving car to (`distance1`-`distance2`)/0.5 (unit: cm/s)
![auto_fit](images/Case5/Case5_p2.png)<P>

<span id="subtitle">Step 3. Calculate car speed</span><P>
* In block `forever`, call function `calculate_Speed` from `Advanced` > `Functions` to get the speed of the moving car
* Snap `If statement` into the loop
* If `speed ≥0`, then it will `plot bar graph of …` from `Led` and draw variable `speed` into the plotted value. Set value up to 20 
* Snap `clear OLED display` from `OLED` to avoid overlap
* Snap `show string` and show value of variables `distance1`, `distance2` and `speed`
![auto_fit](images/Case5/Case5_p3.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_0Y0h5MWPde4A](https://makecode.microbit.org/_0Y0h5MWPde4A)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_0Y0h5MWPde4A" width="100%" height="500" frameborder="0"></iframe>


## Results
<HR>

It will keep checking the distance of cars from distance sensor by distance sensor in every 500ms. The speed of the cars will be shown on OLED. A bar chart of speed will be shown on micro:bit LED also.<BR><P>
![auto_fit](images/Case5/Case5_result.gif)<P>

## Think
<HR>

How can we set a sound alert to notify that there is car over-speeding?<BR><P>

