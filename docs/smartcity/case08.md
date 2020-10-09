# IoT Case 08: Automated Traffic Light

Level: ![level](images/level3.png)


## Sender
<HR>

### Goal
<HR>

Make a sender to send signal to another micro:bit to show if there is traffic jam or not.<BR><P>

### Background
<HR>

<span id="subtitle">How to send signal to another micro:bit?</span><P>
Micro:bit (sender and receiver) are connected to the same channel so wifi message can be sent between the micro:bit. Such that when the sender micro:bit sends a Wi-Fi message “trafficjam” to receiver micro:bit. When receiver micro:bit receives a WiFi message “trafficjam”, the connected traffic light will turn red.<BR><P>

<span id="subtitle">Sender micro:bit operation</span><P>
When the light value detected is too low, this would represent there is a traffic jam and and a ‘trafficjam’ wifi message to another microbit. When the light value detected is high, this would represent there is no traffic jam and send a “nojam” wifi message to another micro:bit.<BR><P>
![pic_90](images/Case8/Concept-diagram-Case8_sender.png)<P>

### Part List
<HR>

<table><tr><td>
Electronics:
<ul display='inline-block'>
<li>micro:bit X1</li>
<li>IoT:bit (with OLED) X1</li>
<li>3-pin module wire X1</li>
&nbsp;&nbsp;1. Light Sensor X1<BR>
</ul>
</td></tr>
<tr><td>Equipment:
<ul><li>ScrewDriver X1</li></ul></td></tr></table>

![auto_fit](images/Case8/Case8a_parts.png)<P>

 
### Assembly step
<HR>

N/A

### Hardware connect
<HR>

Connect the Light Sensor to P0 port of IoT:bit<BR><P>
![auto_fit](images/Case8/Case8a_hardware.png)<P>


### Programming (MakeCode)
<HR>

<span id="subtitle">Step 1</span><P>
Drag on start block from Basic. Drag Initialize IoT:bit at OLED from IoT:bit, set OLED height:64, width:128. Set WiFi to ssid “wifi_name” and pwd “WiFi_password”.<BR><P>
![auto_fit](images/Case8/Case8a_p1.png)<P>

<span id="subtitle">Step 2</span><P>
Set light to 0 and set status and check status to “” from variable and text.<BR><P>
![auto_fit](images/Case8/Case8a_p2.png)<P>

<span id="subtitle">Step 3</span><P>
Drag forever block from Basic. Snap if statement into forever. Set if WiFi is connected then.<BR><P>
![auto_fit](images/Case8/Case8a_p3.png)<P>

<span id="subtitle">Step 4</span><P>
Set light to get percentage value (percentage) at Pin P0 from variables and Smartcity and show number light from OLED.<BR><P>
![auto_fit](images/Case8/Case8a_p4.png)<P>

<span id="subtitle">Step 5</span><P>
Set if light < 50 then, set check_status to “trafficjam”. That’s say there is traffic jam on the road (i.e. light sensor value < 50 and therefore set check_status to “trafficjam”.<BR><P>
![auto_fit](images/Case8/Case8a_p5.png)<P>

<span id="subtitle">Step 6</span><P>
Else, set check_status to “nojam”.<BR><P>
![auto_fit](images/Case8/Case8a_p6.png)<P>

<span id="subtitle">Step 7</span><P>
If status ≠ check_status then, set status to check status and WiFi send message (status) in channel “traffic”.<BR><P>
![auto_fit](images/Case8/Case8a_p7.png)<P>

<span id="subtitle">Step 8</span><P>
Pause for 1000ms.<BR><P>
![auto_fit](images/Case8/Case8a_p8.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_EroCeHYWbeiC](https://makecode.microbit.org/#pub:_EroCeHYWbeiC)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_EroCeHYWbeiC" width="100%" height="500" frameborder="0"></iframe>


### Result
<HR>

Light sensor is used to detect if there are traffic jam. Once the light intensity is not low, it indicates that there is a traffic jam on the road. Wi-Fi message “nojam” will be sent to another micro:bit (receiver).<BR><P>
![auto_fit](images/Case8/Case8a_result1.png)<P>
Once the light intensity is too low, it indicates that there is a traffic jam on the road. Wi-Fi message “trafficjam” will be sent to another micro:bit (receiver).<BR><P>
![auto_fit](images/Case8/Case8a_result2.png)<P>

### Think
<HR>

Q1. How can we use distance sensor to detect traffic status?<BR><P>


## Receiver
<HR>

### Goal
<HR>

Make an auto-traffic LED Module by receiving signal from sender micro:bit.<BR><P>

### Background
<HR>

<span id="subtitle">How to receive signal from another micro:bit?</span><P>
Micro:bit (sender and receiver) are connected to the same channel so wifi message can be sent between the micro:bit. If receiver micro:bit receives a WiFi message “trafficjam” from sender, the connected traffic light will turn red.<BR><P>

<span id="subtitle">Receiver micro:bit operation</span><P>
When a wifi message “trafficjam” is received, it means there is traffic jam forward. The traffic LED Module will turn red. When a wifi message “nojam” is received, it means there is no traffic jam forward. The traffic LED Module will turn green. By using smart traffic light, the problem of traffic jam can be reduced as automatic traffic control is used.<BR><P>
![pic_90](images/Case8/Concept-diagram-Case8_receiver.png)<P>

### Part List
<HR>

<table><tr><td>
Electronics:
<ul display='inline-block'>
<li>micro:bit X1</li>
<li>IoT:bit(with OLED) X1</li>
<li>3-pin module wire X1 </li>
&nbsp;&nbsp;1. Traffic LED Module X1<BR>
</ul>
</td></tr>
<tr>
<td>Model:
<ul>
<li>Traffic light stand Model G1-G2 X1</li>
<li>M4 Screws X2</li>
<li>M4 Nuts X2</li>
</ul>
</td></tr>
<tr><td>Equipment:
<ul><li>ScrewDriver X1</li></ul></td></tr></table>

![auto_fit](images/Case8/Case8b_parts.png)<P>

### Assembly step
<HR>

<span id="subtitle">Step 1</span><P>
Attach the Traffic light Module to G1 model using M4 screw and nut.<BR><P>
![auto_fit](images/Case8/Case8b_po1.png)<P>


<span id="subtitle">Step 2</span><P>
Put together all the cardboard parts (G1-G2)<BR><P>
![auto_fit](images/Case8/Case8b_po2.png)<P>
 
 


### Hardware connect
<HR>

Connect the Traffic LED Module to P0 port of IoT:bit<BR><P>
![auto_fit](images/Case8/Case8b_hardware.png)<P>


### Programming (MakeCode)
<HR>

<span id="subtitle">Step 1</span><P>
Drag on start block from Basic. Drag Initialize IoT:bit at OLED from IoT:bit, set OLED height:64, width:128. Set WiFi to ssid “wifi_name” and pwd “WiFi_password”.<BR><P>
![auto_fit](images/Case8/Case8b_p1.png)<P>

<span id="subtitle">Step 2</span><P>
On WiFi connected, WiFi start listening in channel ‘traffic’ from IoT:bit and IoT:bit – channel.<BR><P>
![auto_fit](images/Case8/Case8b_p2.png)<P>

<span id="subtitle">Step 3</span><P>
Drag On WiFi received WiFiMessage from IoT:bit. <BR><P>
If WiFiMessage = “trafficjam” then, call TurnRed. That’s say if the received message is traffic jam, call the traffic light to turn red.<BR><P>
![auto_fit](images/Case8/Case8b_p3.png)<P>

<span id="subtitle">Step 4</span><P>
Else if WiFiMessage = “nojam” then, call TurnGreen. That’s say if the received message is no traffic jam, call the traffic light to turn green.<BR><P>
![auto_fit](images/Case8/Case8b_p4.png)<P>

<span id="subtitle"> Stet 5</span><P>
Set up a new function (TurnRed). Control traffic light at P0 green on from SmartCity and pause for 2000ms from basic, then control traffic light at P0 yellow on and pause for 2000ms. Lastly, control traffic light at P0 red on and pause for 2000ms.<BR><P>
![auto_fit](images/Case8/Case8b_p5.png)<P>

<span id="subtitle">Step 6</span><P>
Set up a new function (TurnGreen). Control traffic light at P0 red on from SmartCity and pause for 2000ms from basic, then control traffic light at P0 red and yellow on and pause for 2000ms. Lastly, control traffic light at P0 green on and pause for 2000ms.<BR><P>
![auto_fit](images/Case8/Case8b_p6.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_hjoATDhYTMqd](https://makecode.microbit.org/#pub:_hjoATDhYTMqd)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_hjoATDhYTMqd" width="100%" height="500" frameborder="0"></iframe>


### Result
<HR>

By receiving wifi message, traffic LED Module will turn to the corresponding colour automatically.
If there are no traffic jam ahead (detected by light sensor). Micro:bit (sender) will send wifi message “nojam” to the micro:bit (receiver). The traffic light will turn green.
If there are traffic jam ahead (detected by light sensor). Micro:bit (sender) will send wifi message “nojam” to the micro:bit (receiver). The traffic light will turn red.
<BR><P>
![auto_fit](images/Case8/Case8b_result.gif)<P>

### Think
<HR>

Q1. How can we add sound effect to the traffic LED Module according to the corresponding color?<BR><P>
