# IoT Case 11: Roof garden clothes rack

Level: ![level](images/level4.png)
![auto_fit](images/Case11/case-11.png)<P>

## Goal
<HR>

Make a smart roof garden clothes rack, once the weather condition is changed, the rack can be opened/ closed automatically.

## Background
<HR>

<span id="subtitle">What is Roof garden clothes rack?</span><BR><P>
People no long need to rush up to the roof when raining as the clothes rack can be closed automatically even when house owner is not at home.<BR><P>
<span id="subtitle">Roof garden clothes rack operation</span><BR><P>
Micro:bit can receive WAN commands from WAN (eg. IFTTT), the the micro:bit will get the command name. If the command name is “Rain”, the servo will turn to 90ᵒ and the rack will be opened. If the command name is “Clear”, the servo will turn to 180ᵒ and the rack will be closed.<BR><P>
![auto_fit](images/Case11/Concept-diagram-Case11.png)<P>

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
![pic_60](images/Case11/Case11_ass5.png)<P>
![auto_fit](images/Case11/Case11_ass6.png)<P>
<span id="subtitle">Step 6</span><BR><P>
Step 6. Assembly completed!<BR><P>
![pic_40](images/Case11/Case11_ass7.png)<P>


## Hardware connect
<HR>

Connect the 180ᵒ Servo to P1 port of IoT:bit<BR><P>

Micro:bit P1|Servo
:-: | :-: 
S (yellow) |S (orange)
V (red)	| V (red)
G (black) | G (brown)

![auto_fit](images/Case11/Case11_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize OLED, IoT:bit and connect to WiFi</span><BR><P>
* Snap `Initialize OLED with width:128, height: 64` to `on start`
* Snap `Initialize IoT:bit TX P16 RX P8` from `IoT:bit` to `on start`
* Snap `Set Wi-Fi to ssid pwd` from `IoT:bit`
* Enter your Wi-Fi name and password. Here we set `smarthon` as `SSID` and `12345678` as `password`
![pic_60](images/Case11/Case11_p1.png)<P>

<span id="subtitle">Step 2. Show icon “tick” after WiFi connection</span><BR><P>
* Snap `show icon` from `basic` to `On WiFi connected` and select icon `tick`
* Draw the `Device ID` variable from `On WiFi connected` to the `show string` block placeholder
![pic_50](images/Case11/Case11_p2.png)<P>

<span id="subtitle">Step 3. Receive WAN command</span><BR><P>
* Go to OLED
* Snap the `clear OLED display` to `On WiFi received` to avoid overlap
* Snap the `show string` to `On WiFi received`
* Draw the `WAN_Command` variable to show string placeholder
![pic_70](images/Case11/Case11_p3.png)<P>

<span id="subtitle">Step 4. Control rack open/close by WAN command</span><BR><P>
* Snap `if-condition`
* Set variable `WAN_Command` = `Rain` into `if-condition`
* Snap `Turn Servo to … degree` from `SmartCity` > `Output`
* `Set Servo degree to 90 at P1` (control the servo to open the rack)
* Set variable `WAN_Command` = `Clear` into `else-if-condition`
* Snap `Turn Servo to … degree` from `SmartCity` > `Output`
* `Set Servo degree to 180 at P1` (control the servo to close the rack)
![auto_fit](images/Case11/Case11_p4.png)<P>

<span id="subtitle">Step 5. Press A to open clothes rack</span><BR><P>
* Snap `on button … pressed` from `Input`, set button `A`
* Snap `Turn Servo to…` from `SmartCity` > `Output`
* `Set servo to 90 degree at P1` (open clothes rack)
![pic_50](images/Case11/Case11_p5.png)<P>

<span id="subtitle">Step 6. Press B to close clothes rack</span><BR><P>
* Snap `on button … pressed` from `Input`, set button `B`
* Snap `Turn Servo to…` from `SmartCity` > `Output`
* `Set servo to 180 degree at P1` (close clothes rack)
![pic_50](images/Case11/Case11_p6.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_6KyfVPJEd10A](https://makecode.microbit.org/_6KyfVPJEd10A)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_6KyfVPJEd10A" width="100%" height="500" frameborder="0"></iframe>


## IoT (IFTTT)
<HR>

<span id="remarks">* For the setting of IFTTT, please refer to “Chapter 4: Cloud Control micro:bit by IFTTT”</span><BR><P>

<span id="subtitle">Step 1. Create applet in IFTTT<BR><P>
![auto_fit](images/Case11/Case11_iot1.png)<P>


## Result
<HR>

The micro:bit is controlled by IFTTT (trigger by weather open data). When the weather condition change to “Rain”, the cloth rack will be opened. When the weather condition change to “Clear”, the cloth rack will be closed.<BR><P>
![auto_fit](images/Case11/Case11_result.gif)<P>

## Think
<HR>

Q1. Can you control the clothes rack by other weather conditions? (e.g. sunlight)<BR><P>
