# IoT Case 09: Smart House door control 

Level: ![level](images/level4.png)


## Goal
<HR>

Use app inventor to create an APP to control the door of the house. <BR><P>

## Background
<HR>

<span id="subtitle">What is app inventor?</span><BR><P>
App Inventor allows user to develop their own app for Android phones by simple programming and design work.<BR><P>
<span id="subtitle">Smart House door operation</span><BR><P>
When the micro:bit receives the signal “opendoor” from the app, the 180o servo will turn for 180o to open the door. When the micro:bit receives the signal “closedoor” from the app, the 180o servo will turn back 180o to close the door.<BR><P>

## Part List
<HR>

<table><tr><td>
Electronics:
<ul display='inline-block'>

<li>micro:bit X1</li>
<li>IoT:bit(with OLED) X1</li>
&nbsp;&nbsp;1. 180ᵒ servo X1<BR>
</ul>
</td></tr>
<tr>
<td>Model:
<ul>
<li>House Model H1-H2 X1</li>
<li>L-shaped stand X1</li>
<li>Paper Clip X1</li>
<li>M3 Screw x 10mm X2</li>
<li>M3 Nut X2</li>
<li>Servo M2 sharp screw X1</li>
</ul>
</td></tr>
<tr><td>Equipment:
<ul><li>ScrewDriver X1</li></ul></td></tr></table>

![auto_fit](images/Case9/Case9_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step 1</span><BR><P>
Attach the L-shaped stand with paper clip to the model H1<BR><P>

<span id="subtitle">Step 2</span><BR><P>
Straighten the paper clip and cut it to 6.5 cm<BR><P>

<span id="subtitle">Step 3</span><BR><P>
Use pilers to fix the paper clip into the L-shaped stand<BR><P>
![auto_fit](images/Case9/Case9_po1.png)<P>

<span id="subtitle">Step 4</span><BR><P>
Make a small hole to fix into the stand securely<BR><P>
![auto_fit](images/Case9/Case9_po2.png)<P>

<span id="subtitle">Step 5</span><BR><P>
Attach the servo to the model H1<BR><P>
![auto_fit](images/Case9/Case9_po3.png)<P>
<span id="subtitle">Step 6</span><BR><P>
Put together all the cardboard parts (H1-H2)<BR><P>
![auto_fit](images/Case9/Case9_po4.png)<P>



 

## Hardware connect
<HR>

Connect the 180ᵒ servo to P2 port of IoT:bit<BR><P>

Micro:bit P2|Servo
-:-|-:-
S (yellow)|S (orange)
V (red)|V (red)
G (black)|G (brown)

![auto_fit](images/Case9/Case9_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1</span><BR><P>
Drag on start block from Basic. Drag Initialize IoT:bit at OLED from IoT:bit, set OLED height:64, width:128. Set WiFi to ssid “wifi_name” and pwd “WiFi_password”.<BR><P>
![auto_fit](images/Case9/Case9_p1.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Turn servo to 180 degree at P2 from Smartcity.<BR><P>
![auto_fit](images/Case9/Case9_p2.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Drag On WiFi connected and start WiFi remote control (WAN) from IoT:bit.<BR><P>
![auto_fit](images/Case9/Case9_p3.png)<P>
<span id="subtitle">Step 4</span><BR><P>
Drag on WAN command received (WAN_Command) from IoT:bit. <BR><P>
If WAN_Command = opendoor then, turn servo to 45 degree at P2 from Smartcity.<BR><P>
![auto_fit](images/Case9/Case9_p4.png)<P>
<span id="subtitle">Step 5</span><BR><P>
Else if WAN_Command = closedoor then, turn servo to 180 degree at P2 from Smartcity.<BR><P>
![auto_fit](images/Case9/Case9_p5.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_L2V0LeAHo0hg](https://makecode.microbit.org/#pub:_L2V0LeAHo0hg)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_L2V0LeAHo0hg" width="100%" height="500" frameborder="0"></iframe>

 
## (IoT (App Inventor)
<HR>

<span id="remarks">* For more details, please refer to “Chapter 3: Control your micro:bit by App Inventor 2”.</span><BR><P>

<span id="subtitle">Step 1</span><BR><P>
Create the page with the components<BR><P>
* On Designer:
* Drag the components from the left menu – we will need buttons to open or close the door and a textbox for input the Device ID number. 
* Also, add the invisible component “Web” under connectivity, we will need it for WAN connection.
![auto_fit](images/Case9/Case9_iot1.png)<P>


<span id="subtitle">Step 2</span><BR><P>
Make the programming part
* On Blocks: 
* The WAN control command URL is: 
[http://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand](http://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand)

* When Button1 is clicked, it will direct to the URL with given device ID and command “opendoor”.
![auto_fit](images/Case9/Case9_iot2.png)<P>
* When Button2 is clicked, it will direct to the URL with given device ID and command “closedoor”.
![auto_fit](images/Case9/Case9_iot3.png)<P>
* Download the App in your phone to by .apk or scan QR code.
![auto_fit](images/Case9/Case9_iot4.png)<P>
 
## Result 
Input your device ID number in the textbox, then click button “opendoor” to send command “opendoor”. Click button “Close Door” to send command “closedoor”.<BR><P>
![auto_fit](images/Case9/Case9_result1.png)<P>

Micro:bit will wait for WAN command: <BR><P>
![auto_fit](images/Case9/Case9_result2.png)<P>
 
![auto_fit](images/Case9/Case9_result3.png)<P>

With app inventor and micro:bit, you can control the door open/close by mobile app!<BR><P>
![auto_fit](images/Case9/Case9_result4.gif)<P>


## Think
<HR>

Q1. How can we add password authentication to open the door?<BR><P>
Q2. We can install the servo to different position in the house (tips: modify the turning angle of the servo)<BR><P>
