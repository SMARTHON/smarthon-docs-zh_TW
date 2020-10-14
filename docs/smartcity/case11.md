# IoT Case 11: Roof garden clothes rack

Level: ![level](images/level5.png)
![auto_fit](images/Case11/case-11.png)<P>

## Goal
<HR>

Make a smart roof garden clothes rack, once raindrop is detected, the rack can be opened automatically.

## Background
<HR>

People no long need to rush up to the roof when raining as the clothes rack can be closed automatically even when house owner is not at home.
Smart roof garden operation
When raindrop sensor sensed that it is raining, it will send a signal to micro:bit and therefore the clothes rack will be opened. When there is no rain, the clothes rack will be closed.
Also, micro:bit can receive WAN commands from WAN (eg. IFTTT), the the micro:bit will get the command name. If the command name is “rain”, the servo will turn to 90ᵒ and the rack will be opened. If the command name is “clear”, servo will turn to 180ᵒ and the rack will be closed.
![pic_90](images/Case11/Concept-diagram-Case11.png)<P>

## Part List
<HR>


![auto_fit](images/Case11/Case11_parts.png)<P>
 
## Assembly step
<HR>

<span id="subtitle">Step 1</span><BR><P>
Step 1. Attach the raindrop sensor to the model H2<BR><P>
![auto_fit](images/Case11/Case11_ass1.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Step 2. Attach the long stand (H3) to the model H1<BR><P>
![auto_fit](images/Case11/Case11_ass2.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Step 3. Put together all the cardboard parts.<BR><P>
![auto_fit](images/Case11/Case11_ass3.png)<P>
<span id="subtitle">Step 4</span><BR><P>
Step 4. Screw the cloth rack (H5) onto the 180ᵒ servo using M2 screws  <BR><P>
![auto_fit](images/Case11/Case11_ass4.png)<P>
<span id="subtitle">Step 5</span><BR><P>
Step 5. Put together the models H4-H5 and H6-H7. <BR><P>
![auto_fit](images/Case11/Case11_ass5.png)<P>
![auto_fit](images/Case11/Case11_ass6.png)<P>
<span id="subtitle">Step 6</span><BR><P>
Step 6. Assembly completed!<BR><P>
![auto_fit](images/Case11/Case11_ass7.png)<P>


## Hardware connect
<HR>

Connect the Raindrop sensor to P0 port of IoT:bit<BR><P>
Connect the 180ᵒ Servo to P1 port of IoT:bit<BR><P>

Micro:bit P1|Servo
:-: | :-: 
S (yellow) |S (orange)
V (red)	| V (red)
G (black) | G (brown)

![auto_fit](images/Case11/Case11_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1</span><BR><P>
Drag on start block fro Basic. Drag Initialize IoT:bit at OLED from IoT:bit, set OLED height:64, width:128. Set WiFi to ssid “wifi_name” and pwd “WiFi_password”.<BR><P>
![auto_fit](images/Case11/Case11_p1.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Set raindrop to 0.<BR><P>
![auto_fit](images/Case11/Case11_p2.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Set Forcast_rain to false.<BR><P>
![auto_fit](images/Case11/Case11_p3.png)<P>
<span id="subtitle">Step 4
span><BR><P>Turn servo to 180 degree at P1 from Smartcity. The rack is closed.<BR><P>
![auto_fit](images/Case11/Case11_p4.png)<P>
<span id="subtitle">Step 5</span><BR><P>
Drag On WiFi connected and start WiFi remote control (WAN) from IoT:bit.<BR><P>
![auto_fit](images/Case11/Case11_p5.png)<P>
<span id="subtitle">Step 6</span><BR><P>
Drag on WAN command received (WAN_Command) from IoT:bit.<BR><P>
![auto_fit](images/Case11/Case11_p6.png)<P>
<span id="subtitle">Step 7</span><BR><P>
If WAN_Command = clear then, set Forcast_rain to false.<BR><P>
![auto_fit](images/Case11/Case11_p7.png)<P>
<span id="subtitle">Step 8</span><BR><P>
Else (i.e. WAN_Command ≠ clear, set Forcast_rain to true).<BR><P>
![auto_fit](images/Case11/Case11_p8.png)<P>
<span id="subtitle">Step 9</span><BR><P>
Drag forever block from Basic. Set raindrop to get raindrop value (percentage) at Pin P0 and show number raindrop from OLED.<BR><P>
![auto_fit](images/Case11/Case11_p9.png)<P>
<span id="subtitle">Step 10</span><BR><P>
Snap if statement into forever. Set if raindrop > 5 (raining) or Forcast_rain=true (it will rain) then.<BR><P>
Snap turn Servo to 90 degree at P1 from Smartcity. That’s say the rack can be opened.<BR><P>
![auto_fit](images/Case11/Case11_p10.png)<P>
<span id="subtitle">Step 11</span><BR><P>
Else, turn servo to 180 degree at P1. That’s say the rack will be closed otherwise.<BR><P>
![auto_fit](images/Case11/Case11_p11.png)<P>
<span id="subtitle">Step 12</span><BR><P>
Pause for 15000ms.<BR><P>
![auto_fit](images/Case11/Case11_p12.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_UC24pMak66dT](https://makecode.microbit.org/#pub:_UC24pMak66dT)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_UC24pMak66dT" width="100%" height="500" frameborder="0"></iframe>


## IoT (IFTTT)
<HR>

<span id="remarks">For the setting of IFTTT, please refer to “Chapter 4: Control your micro:bit by IFTTT Services”</span><BR><P>

<span id="subtitle">Step 1</span><BR><P>
Create applet (If Weather Underground then Smarthon)<BR><P>
![auto_fit](images/Case11/Case11_iot1.png)<P>
If it is at 06:00pm, send WAN control command: light_on to the micro:bit<BR><P>
![auto_fit](images/Case11/Case11_iot1.png)<P>


## Result
<HR>

The micro:bit is controlled by IFTTT (trigger by weather open data). When the weather condition change to “rain”, the cloth rack will be opened. When the weather condition change to “clear”, the cloth rack will be closed.<BR><P>
![auto_fit](images/Case11/Case11_result.gif)<P>

## Think
<HR>

Q1. How to notify the house owner the weather status (rain) by email through IFTTT?<BR><P>
