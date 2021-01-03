# IoT Case 09: Smart House door control 

Level: ![level](images/level4.png)
![auto_fit](images/Case9/case-09.png)<P>

## Goal
<HR>

Use app inventor to create an APP to control the door of the house. <BR><P>

## Background
<HR>

<span id="subtitle">What is app inventor?</span><BR><P>
App Inventor allows user to develop their own app for Android phones by simple programming and design work.<BR><P>
<span id="subtitle">Smart House door operation</span><BR><P>
When the micro:bit receives the signal “opendoor” from the app, the 180o servo will turn for 180o to open the door. When the micro:bit receives the signal “closedoor” from the app, the 180o servo will turn back 180o to close the door.<BR><P>
![auto_fit](images/Case9/Concept-diagram-Case9.png)<P>

## Part List
<HR>

![auto_fit](images/Case9/Case9_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step 1</span><BR><P>
Attach the L-shaped stand with M4 screws and nuts to the model H1. Make a small hole to fix into the stand securely.<BR><P>
![auto_fit](images/Case9/Case9_ass1.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Attach the servo to the model H1.<BR><P>
![auto_fit](images/Case9/Case9_ass2.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Straighten the paper clip and cut it to 6.5 cm. Use pilers to fix the paper clip into the L-shaped stand.<BR><P>
![auto_fit](images/Case9/Case9_ass3.png)<P>
<span id="subtitle">Step 4</span><BR><P>
Put together all the cardboard parts (H1-H2)<BR><P>
![auto_fit](images/Case9/Case9_ass4.png)<P>
<span id="subtitle">Step 5</span><BR><P>
Assembly completed!<BR><P>
![pic_50](images/Case9/Case9_ass5.png)<P>


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

<span id="subtitle">Step 1. Initialize OLED, IoT:bit and connect to WiFi
* Snap `Initialize OLED with width:128, height: 64` to `on start`
* Snap `Initialize IoT:bit TX P16 RX P8` from `IoT:bit` to `on start`
* Snap `Set Wi-Fi to ssid pwd` from `IoT:bit`
* Enter your Wi-Fi name and password. Here we set `smarthon` as `SSID` and `12345678` as `password`
![pic_60](images/Case9/Case9_p1.png)<P>

<span id="subtitle">Step 2. Set servo initial position</span><BR><P>
* Snap `Turn Servo to … degree` from `SmartCity` > `Output`
* Turn servo to `180` degree at pin `P2` (the servo will control the door to be closed initially)
![pic_60](images/Case9/Case9_p2.png)<P>

<span id="subtitle">Step 3. Show icon “tick” after WiFi connection</span><BR><P>
* Snap `show icon` from `basic` to `On WiFi connected` and select icon `tick`
* Draw the `Device ID` variable from `On WiFi connected` to the `show string` block placeholder
![pic_60](images/Case9/Case9_p3.png)<P>

<span id="subtitle">Step 4. Receive WAN command</span><BR><P>
* Go to OLED
* Snap the` clear OLED display` to `On WiFi received` to avoid overlap
* Snap the `show string` to `On WiFi received`
* Draw the `WAN_Command` variable to show string placeholder
![pic_80](images/Case9/Case9_p4.png)<P>

<span id="subtitle">Step 5. Open/close door by WAN command</span><BR><P>
* If Wan command `opendoor` is received, `turn servo to 45 degree at P2` (open door angle)
* If Wan command `closedoor` is received, `turn servo to 180 degree at P2` (close door angle)
![pic_80](images/Case9/Case9_p5.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_FKDKfDYj1Le1](https://makecode.microbit.org/#pub:_FKDKfDYj1Le1)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_FKDKfDYj1Le1" width="100%" height="500" frameborder="0"></iframe>

 
## IoT (App Inventor)
<HR>

<span id="remarks">* For more details, please refer to “Chapter 3: Direct control micro:bit by App Inventor 2”</span><BR><P>


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

 
![auto_fit](images/Case9/Case9_result3.png)<P>

With app inventor and micro:bit, you can control the door open/close by mobile app!<BR><P>
![auto_fit](images/Case9/Case9_result4.gif)<P>


## Think
<HR>

Q1. How can we add password authentication to open the door?<BR><P>
Q2. We can install the servo to different position in the house (tips: modify the turning angle of the servo)<BR><P>
