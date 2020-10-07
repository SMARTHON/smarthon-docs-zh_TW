# Case 04: Urban noise detection

Level: ![level](images/level1.png)
![pic_70](images/Case4/case-04.png)<P>

## Goal
<HR>

Make a noise detection point to detect the noise volume near the roadside using noise sensor.<BR><P>

## Background
<HR>

<span id="subtitle">What is urban noise detection?</span><P>
It is a system to detect noise near the road as noise pollution caused by cars on the road seriously affect the living standard of people. By installing a monitor to detect the noise volume near the roadside can help engineer to gather noise information and find solution to solve the problem in the future.<BR><P>

<span id="subtitle">Noise detection operation</span><P>
The noise sensor can detect the volume in dB near the roadside and show the volume on the OLED. A bar graph of sound intensity will be shown on the micro:bit.<BR><P>



## Part List
<HR>

<table><tr><td>
Electronics:
<ul display='inline-block'>

<li>micro:bit X1</li>
<li>IoT:bit (with OLED) X1</li>
<li>OLED extension wire X1</li>
<li>3-pin module wire X1</li>
&nbsp;&nbsp;1. Noise Sensor X1<BR>

</ul>
</td></tr>
<tr>
<td>Model:
<ul>
<li>Noise detection stand Model D1-D2 X1</li>
<li>M4 Screws X2</li>
<li>M4 Nuts X2</li>
<li>M2 Screws X4</li>
<li>M2 Nuts X4</li>
</ul>
</td></tr>
<tr><td>Equipment:
<ul><li>ScrewDriver X1</li></ul></td></tr></table>

![pic](images/Case4/Case4_parts.png)<P>

## Assembly step 
<HR>

<span id="subtitle">Step 1</span><P>
Attach the OLED to D1 model with M2 x10mm screws and nuts.<BR><P>
![pic](images/Case4/Case4_po1.png)<P>
<span id="subtitle">Step 2</span><P>
Attach noise sensor to D1 model with M4 screws and nuts.<BR><P>
![pic](images/Case4/Case4_po2.png)<P>
<span id="subtitle">Step 3</span><P>
Put together all the cardboard parts (D1-D2).<BR><P>
![pic](images/Case4/Case4_po3.png)<P>

## Hardware connect
<HR>

Connect Noise Sensor to P1 port of IoT:bit<BR><P>
Extend the connection of OLED to I2C connection port of IoT:bit<BR><P>
![pic](images/Case4/Case4_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1</span><P>
Drag on start block from Basic. Drag Initialize IoT:bit at OLED from IoT:bit, set OLED height:64, width:128. Set noise to 0 from variables.<BR><P>
![pic](images/Case4/Case4_p1.png)<P>
<span id="subtitle">Step 2</span><P>
Drag forever block from Basic. Set noise to round get noise level (dB) at pin P1.<BR><P>
![pic](images/Case4/Case4_p2.png)<P>
<span id="subtitle">Step 3</span><P>
Show string Noise: noise (variable) dB by using join from text.<BR><P>
![pic](images/Case4/Case4_p3.png)<P>
<span id="subtitle">Step 4</span><P>
Plot bar graph of noise up to 100 from LED, which means showing a bar graph on Micro:bit based on the recorded sound level.<BR><P>
![pic](images/Case4/Case4_p4.png)<P>
<span id="subtitle">Step 5</span><P>
Pause for 0.5 second.<BR><P>
![pic](images/Case4/Case4_p5.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_RqJ2yEJaVMEk](https://makecode.microbit.org/#pub:_RqJ2yEJaVMEk)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_RqJ2yEJaVMEk" width="100%" height="500" frameborder="0"></iframe>


## Results
<HR>

After initializing WiFi extension board and OLED, micro:bit will show a bar graph for the sound intensity in a city.<BR><P>
![pic](images/Case4/Case4_result.gif)<P>
![pic](images/Case4/Case4_result2.png)<P>
## Think
<HR>

Q1. How to make a notification if noise pollution problem is serious? i.e. showing red LED<BR><P>

