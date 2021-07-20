# IoT Case 07: Smart defense system

Level: ![level](images/level3.png)
![auto_fit](images/Case7/case-07.png)<P>

## Goal
<HR>

Make a smart defense system which emits sound and sends an email to the house owner if there are any suspicious movement near the door.<BR><P>

## Background
<HR>

<span id="subtitle">What is IFTTT?</span><BR><P>
IFTTT can help connect all your different apps and devices which enables them to work together to do specific tasks.<BR><P>
<span id="subtitle">Smart defense system operation</span><BR><P>
The motion sensor can deliver a motion signal to the micro:bit. When the micro:bit detects the signal, the buzzer will emit sound and send an email to specific email account through IFTTT. Also, a monstor icon will be shown on the micro:bit if there are suspicious people passes by.<BR><P>
![auto_fit](images/Case7/Concept-diagram-Case7.png)<P>

## Part List
<HR>

![auto_fit](images/Case7/Case7_parts.png)<P>

## Assembly step 
<HR>

<span id="subtitle">Step 1</span><BR><P>
Attach the motion sensor to F1 model.
![auto_fit](images/Case7/Case7_ass1.png)<P>
![auto_fit](images/Case7/Case7_ass2.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Put together all the cardboard parts (F1-F2)
![auto_fit](images/Case7/Case7_ass3.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Assembly completed!
![pic_60](images/Case7/Case7_ass4.png)<P>


## Hardware connect
<HR>

Connect the Motion Sensor to P1 port of IoT:bit<BR><P>
Turn on the Buzzer Switch on P0 port of IoT:bit<BR><P>
![auto_fit](images/Case7/Case7_hardware.png)<P>

## IoT (IFTTT)
<HR>

<span id="remarks">* For more details, please refer to Chapter 2: Send Email by IFTTT </span><BR><P>

<span id="subtitle">Step 1</span><BR><P>
Go to [https://ifttt.com](https://ifttt.com/) , create applet (if webhooks then Email)<BR><P>
![auto_fit](images/Case7/Case7_iot1.png)<P>


<span id="subtitle">Step 2</span><BR><P>
Go to “My services” > “Webhooks”, select “Documentation” . Copy your Webhooks Key as follows:<BR><P>
![auto_fit](images/Case7/Case7_iot2.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize OLED, IoT:bit and connect to WiFi</span><BR><P>
* Snap `Initialize OLED with width:128, height: 64` to `on start`
* Snap `Initialize IoT:bit TX P16 RX P8` from `IoT:bit` to `on start`
* Snap `Set Wi-Fi to ssid pwd` from `IoT:bit`
* Enter your Wi-Fi name and password. Here we set `smarthon` as `SSID` and `12345678` as `password`
![auto_fit](images/Case7/Case7_p1.png)<P>

<span id="subtitle">Step 2: Show icon "tick" after WiFi connection</span><BR><P>
* Snap `show icon` from `basic` to `On WiFi connected` and select icon `tick`
![auto_fit](images/Case7/Case7_p2.png)<P>

<span id="subtitle">Step 3. Check motion sensor value</span><BR><P>
* Snap `if statement` to block `forever`
* If `WiFi is connected`,
* If `get motion (triggered or not) at Pin P1` = `true` then, that’s say someone is near the door.
![auto_fit](images/Case7/Case7_p3.png)<P>
 
<span id="subtitle">Step 4. Send notification when someone pass by </span><BR><P>
* Snap `if statement` to block `forever`
* If `WiFi is connected`, then snap `play tone Middle C for 1 beat` from `music`
* Snap `show icon` from `basic` and select a `monster icon`
* Snap `Send IFTTT key…` from `IoT:bit` > `IoT Services`, input your `IFTTT key` and input event name `SendEmail`
![auto_fit](images/Case7/Case7_p4.png)<P>

<span id="subtitle">Step 5. Show smile icon when no one pass by </span><BR><P>
* Snap `show icon` into `Else`, and select icon `smile` 
* Snap `Pause` after `if statement` to the loop for 1 second delay for checking
![auto_fit](images/Case7/Case7_p5.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_H4uU8R3716xj](https://makecode.microbit.org/_H4uU8R3716xj)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_H4uU8R3716xj" width="100%" height="500" frameborder="0"></iframe>


## Result 
<HR>

When WiFi is connected, if there are any suspicious movement near the door, the buzzer will emit sound and an email will be sent to the house owner. Also, a monster icon will be shown on the micro:bit.<BR><P>
![auto_fit](images/Case7/Case7_result1.png)

![auto_fit](images/Case7/Case7_result2.gif)


## Think
<HR>

Q1. How to avoid sending duplicate emails? (tips: using variable)<BR><P>
Q2. How to distinguish suspicious people (e.g. password authentication)?<BR><P>

