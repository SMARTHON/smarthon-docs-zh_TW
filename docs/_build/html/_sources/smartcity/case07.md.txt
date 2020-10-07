# IoT Case 07: Smart defense system

Level: ![level](images/level3.png)

## Goal
<HR>

Make a smart defense system which emits sound and sends an email to the house owner if there are any suspicious movement near the door.<BR><P>

## Background
<HR>

<span id="subtitle">What is IFTTT?</span><BR><P>
IFTTT can help connect all your different apps and devices which enables them to work together to do specific tasks.<BR><P>
<span id="subtitle">Smart defense system operation</span><BR><P>
The motion sensor can deliver a motion signal to the micro:bit. When the micro:bit detects the signal, the buzzer will emit sound and send an email to specific email account through IFTTT. Also, a monstor icon will be shown on the micro:bit if there are suspicious people passes by.<BR><P>
![pic_80](images/Case7/Concept-diagram-Case7.png)<P>

## Part List
<HR>

<table><tr><td>
Electronics:
<ul display='inline-block'>
<li>micro:bit X1</li>
<li>IoT:bit(with OLED) X1</li>
<li>3-pin module wire X1 </li>
&nbsp;&nbsp;1. Motion Sensor X1<BR>
</ul>
</td></tr>
<tr>
<td>Model:
<ul>
<li>House Model F1-F2 X1</li>
<li>M4 Screws X2</li>
<li>M4 Nuts X2</li>
</ul>
</td></tr>
<tr><td>Equipment:
<ul><li>ScrewDriver X1</li></ul></td></tr></table>

![auto_fit](images/Case7/Case7_parts.png)<P>

## Assembly step 
<HR>

<span id="subtitle">Step 1</span><BR><P>
Attach the motion sensor to F1 model <BR><P>
![auto_fit](images/Case7/Case7_po1.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Put together all the cardboard parts (F1-F2)<BR><P>
![auto_fit](images/Case7/Case7_po2.png)<P>



## Hardware connect
<HR>

Connect the Motion Sensor to P1 port of IoT:bit<BR><P>
Turn on the Buzzer Switch on P0 port of IoT:bit<BR><P>
![auto_fit](images/Case7/Case7_hardware.png)<P>

## IoT (IFTTT)
<HR>

<span id="remarks">* For more details, please refer to Chapter2: Send Email by IFTTT</span><BR><P>
<span id="subtitle">Step 1</span><BR><P>
Go to [https://ifttt.com](https://ifttt.com/) , create applet (if webhooks then Email)<BR><P>
![auto_fit](images/Case7/Case7_iot1.png)<P>


<span id="subtitle">Step 2</span><BR><P>
Go to “My services” > “Webhooks”, select “Documentation” . Copy your Webhooks Key as follows:<BR><P>
![auto_fit](images/Case7/Case7_iot2.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1</span><BR><P>
Drag on start block from Basic. Drag Initialize IoT:bit at OLED from IoT:bit, set OLED height:64, width:128. Set WiFi to ssid “wifi_name” and pwd “WiFi_password”.<BR><P>
![auto_fit](images/Case7/Case7_p1.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Set sendEmail to false from variable and logic.<BR><P>
![auto_fit](images/Case7/Case7_p2.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Drag forever block from Basic. Snap if statement into forever. If WiFi is connected then, add another if statement. If get motion (triggered or not) at Pin P1 = true then, that’s say someone is near the door.<BR><P>
![auto_fit](images/Case7/Case7_p3.png)<P>
<span id="subtitle">Step 4</span><BR><P>
Snap if statement under the above two if statement. If not sendEmail then, set sendEmail to true and send IFTTT key and event_name. That’s say an email will be sent to the house owner once when triggered. <BR><P>
![auto_fit](images/Case7/Case7_p4.png)<P>
<span id="subtitle">Step 5</span><BR><P>
Set play tone Middle C for 1 beat from music and show a monster icon on the micro:bit from basic.<BR><P>
![auto_fit](images/Case7/Case7_p5.png)<P>
<span id="subtitle">Step 6</span><BR><P>
Else, set sendEmail to false from variable and logic and clear screen from more of basic. That’s means there is no email, sound emit and no monster appear if there is no suspicious movement near the door.<BR><P>
![auto_fit](images/Case7/Case7_p6.png)<P>
<span id="subtitle">Step 7</span><BR><P>
Pause for 1000ms after the programming running for one loop.<BR><P>
![auto_fit](images/Case7/Case7_p7.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_TTqYvaYVfWUw](https://makecode.microbit.org/#pub:_TTqYvaYVfWUw)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_TTqYvaYVfWUw" width="100%" height="500" frameborder="0"></iframe>


## Result 
<HR>

When WiFi is connected, if there are any suspicious movement near the door, the buzzer will emit sound and an email will be sent to the house owner. Also, a monster icon will be shown on the micro:bit.<BR><P>
![pic_40](images/Case7/Case7_result1.png)
![pic_40](images/Case7/Case7_result2.gif)


## Think
<HR>

Q1. How to activate the smart defense system only during a certain period?<BR><P>
Q2. How to distinguish suspicious people (e.g. password authentication)?<BR><P>

