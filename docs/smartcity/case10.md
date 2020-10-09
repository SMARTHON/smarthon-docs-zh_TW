# IoT Case 10: Smart Street Light

Level: ![level](images/level4.png)

## Goal
<HR>

Make a smart streetlight which can have a button to control on off.<BR><P>

## Background
<HR>

<span id="subtitle">What is Smart Street Light?</span><BR><P>
To make people living more conveniently, this light can be turned on and off with internal setting withing clicking buttons every day.<BR><P>
<span id="subtitle">Smart Streetlight operation</span><BR><P>
When WAN commands are received from WAN (eg. IFTTT), micro:bit will get the command name. If the command name is “light_on”, the LED light will be turned on. If the command name is “light_off”, the LED light will be turned off.<BR><P>
![pic_90](images/Case10/Concept-diagram-Case10.png)<P>

## Part List
<HR>

<table><tr><td>
Electronics:
<ul display='inline-block'>
<li>micro:bit X1</li>
<li>IoT:bit(with OLED) X1</li>
<li>3-pin Module wire X1</li>
&nbsp;&nbsp;1. White LED Light X1<BR>
</ul>
</td></tr>
<tr>
<td>Model:
<ul>
<li>Smart Street Light Model I1-I3 X1</li>
<li>M4 Screw X2</li>
<li>M4 nut X2</li>
</ul>
</td></tr>
<tr><td>Equipment:
<ul><li>ScrewDriver X1</li></ul></td></tr></table>

![auto_fit](images/Case10/Case10_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step 1</span><BR><P>
Attach the LED light to the model I2 with M4 screw and nuts<BR><P>
![auto_fit](images/Case10/Case10_po1.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Put together all the cardboard parts (I1-I3)<BR><P>
![auto_fit](images/Case10/Case10_po2.png)<P>


## Hardware connect
<HR>

Connect the white LED Light to P1 port of IoT:bit<BR><P>
![auto_fit](images/Case10/Case10_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1</span><BR><P>
Drag on start block from Basic. Drag Initialize IoT:bit at OLED from IoT:bit, set OLED height:64, width:128. Set WiFi to ssid “wifi_name” and pwd “WiFi_password”.<BR><P>
![auto_fit](images/Case10/Case10_p1.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Drag on WiFi connected and start WiFi remote control (WAN) from IoT:bit.<BR><P>
![auto_fit](images/Case10/Case10_p2.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Drag On WAN command received (WAN_command) from IoT:bit.<BR><P>
![auto_fit](images/Case10/Case10_p3.png)<P>
<span id="subtitle">Step 4</span><BR><P>
Drag if statement into On WAN command received (WAN_command) from logic. Set if WAN_command = light_on then, turn white LED to 1023 at P1.<BR><P>
![auto_fit](images/Case10/Case10_p4.png)<P>
<span id="subtitle">Step 5</span><BR><P>
Else if WAN_command = light_off then, turn white LED to 0 at P1.<BR><P>
![auto_fit](images/Case10/Case10_p5.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_cD9TLuDCEH7a](https://makecode.microbit.org/#pub:_cD9TLuDCEH7a)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_cD9TLuDCEH7a" width="100%" height="500" frameborder="0"></iframe>


## IoT (IFTTT)
<HR>

<span id="remarks">* For the setting of IFTTT, please refer to “Chapter 4: Control your micro:bit by IFTTT Services”</span><BR><P>
![auto_fit](images/Case10/Case10_ifttt1.png)<P>
<span id="subtitle">Step 1</span><BR><P>
Create applet (If Date&time then Smarthon)<BR><P>
![auto_fit](images/Case10/Case10_ifttt2.png)<P>




## Result
<HR>

The micro:bit is controlled by IFTTT (trigger by date&time). The LED light will be turned on at 6pm and turned off at 6am every day.<BR><P>
![auto_fit](images/Case10/Case10_result.png)<P>


## Think
<HR>

Q1. How to turn on the light automatically if the today’s weather is cloudy reported by IFTTT.
