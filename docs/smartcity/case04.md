# Case 04: Urban noise detection

Level: ![level](images/level2.png)
![auto_fit](images/Case4/case-04_1.png)<P>

## Goal
<HR>

Make a noise detection point to detect the noise volume near the roadside using noise sensor.<BR><P>

## Background
<HR>

<span id="subtitle">What is urban noise detection?</span><P>
It is a system to detect noise near the road as noise pollution caused by cars on the road seriously affect the living standard of people. By installing a monitor to detect the noise volume near the roadside can help engineer to gather noise information and find solution to solve the problem in the future.<BR><P>

<span id="subtitle">Noise detection operation</span><P>
The noise sensor can detect the volume in dB near the roadside and show the volume on the OLED. A bar graph of sound intensity will be shown on the micro:bit.<BR><P>
![pic_70](images/Case4/Concept-diagram-Case4.png)<P>


## Part List
<HR>

![pic](images/Case4/Case4_parts.png)<P>

## Assembly step 
<HR>

<span id="subtitle">Step 1</span><P>
Attach the OLED to D1 model with M2 * 10mm screws and nuts.<BR><P>
![pic](images/Case4/Case4_ass1.png)<P>
<span id="subtitle">Step 2</span><P>
Attach noise sensor to D1 model with M4 * 10mm screws and nuts.<BR><P>
![pic](images/Case4/Case4_ass2.png)<P>
<span id="subtitle">Step 3</span><P>
Put together all the cardboard parts (D1-D2).<BR><P>
![pic](images/Case4/Case4_ass3.png)<P>
<span id="subtitle">Step 4</span><P>
Assembly completed!<BR><P>
![pic_40](images/Case4/Case4_ass4.png)<P>

## Hardware connect
<HR>

Connect Noise Sensor to P1 port of IoT:bit<BR><P>
Extend the connection of OLED to I2C connection port of IoT:bit<BR><P>
![pic](images/Case4/Case4_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1</span><P>
<span id="subtitle">Step 1. Initialize OLED screen and variable
* Drag `Initialize OLED with width:128, height: 64` to `on start`
* Set `Noise` to 0 from `variables`
![auto_fit](images/Case4/Case4_p1.png)<P>

<span id="subtitle">Step 2. Show noise value on micro:bit LED</span><P>
* In block `forever`. Set `noise` to round `get noise level (dB) at pin P1`
* Drag `plot bar graph of …` from `Led` and draw variable `Noise` into the plotted value. Set value up to 100
* Drag `Pause` to the loop for wait for 0.5 second for next checking
![auto_fit](images/Case4/Case4_p2.png)<P>

<span id="subtitle">Step 3. Show the noise value on OLED screen</span><P>
* Snap `clear OLED display` from `OLED` to avoid overlap
* Snap `show string` to the loop and show value of the variable `Noise`
![auto_fit](images/Case4/Case4_p3.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_TiW9H7CuU5M5](https://makecode.microbit.org/_TiW9H7CuU5M5)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_TiW9H7CuU5M5" width="100%" height="500" frameborder="0"></iframe>


## Results
<HR>

After initializing WiFi extension board and OLED, micro:bit will show a bar graph for the sound intensity in a city.<BR><P>
![pic](images/Case4/Case4_result.gif)<P>
![pic](images/Case4/Case4_result2.png)<P>
## Think
<HR>

Q1. How to make a notification if noise pollution problem is serious? i.e. showing red LED<BR><P>

