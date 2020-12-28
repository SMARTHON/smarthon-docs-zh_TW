# IoT Case 10: Smart Street Light

Level: ![level](images/level4.png)
![auto_fit](images/Case10/case-10.png)<P>

## Goal
<HR>

Make a smart streetlight which can have a button to control on off.<BR><P>

## Background
<HR>

<span id="subtitle">What is Smart Street Light?</span><BR><P>
To improve the living stand of citizen and to save electricity, smart street light can be automatically turned on at night (eg.6pm) and turned off in the morning (eg.6am) <BR><P>
<span id="subtitle">Smart Streetlight operation</span><BR><P>
When WAN commands are received from WAN (eg. IFTTT), micro:bit will get the command name. If the command name is “light_on”, the LED light will be turned on. If the command name is “light_off”, the LED light will be turned off.<BR><P>
![auto_fit](images/Case10/Concept-diagram-Case10.png)<P>

## Part List
<HR>

![auto_fit](images/Case10/Case10_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step 1</span><BR><P>
Attach the LED light to the model I2 with M4 screw and nuts. Put together all the cardboard parts (I1-I3)<BR><P>
![auto_fit](images/Case10/Case10_ass1.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Assembly completed!<BR><P>
![pic_40](images/Case10/Case10_ass2.png)<P>


## Hardware connect
<HR>

Connect the white LED Light to P1 port of IoT:bit<BR><P>
![auto_fit](images/Case10/Case10_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize OLED, IoT:bit and connect to WiFi</span><BR><P>
* Snap `Initialize OLED with width:128, height: 64` to `on start`
* Snap `Initialize IoT:bit TX P16 RX P8` from `IoT:bit` to `on start`
* Snap `Set Wi-Fi to ssid pwd` from `IoT:bit`
* Enter your Wi-Fi name and password. Here we set `smarthon` as `SSID` and `12345678` as `password`
![auto_fit](images/Case10/Case10_p1.png)<P>

<span id="subtitle">Step 2. Show icon “tick” after WiFi connection</span><BR><P>
* Snap `show icon` from `basic` to `On WiFi connected` and select icon `tick`
* Draw the `Device ID` variable from `On WiFi connected` to the `show string` block placeholder
![pic_60](images/Case10/Case10_p2.png)<P>

<span id="subtitle">Step 3. Receive WAN command</span><BR><P>
* Go to OLED
* Snap the` clear OLED display` to `On WiFi received` to avoid overlap
* Snap the `show string` to `On WiFi received`
* Draw the `WAN_Command` variable to show string placeholder
![pic_80](images/Case10/Case10_p3.png)<P>

<span id="subtitle">Step 4. Turn on/off LED by WAN command</span><BR><P>
* Snap `if-condition`
* Set variable `WAN_Command` = `lighton` into `if-condition`
* `turn White LED …` from `SmartCity` > `Output`, turn white LED with intensity: 1023 at P1
* Set variable `WAN_Command` = `lightoff` into `else-if-condition` 
* Snap `turn White LED …` from `SmartCity` > `Output`, turn white LED with intensity: 0 at P1
![auto_fit](images/Case10/Case10_p4.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_ew4HwdDqCaAc](https://makecode.microbit.org/#pub:_ew4HwdDqCaAc)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_ew4HwdDqCaAc" width="100%" height="500" frameborder="0"></iframe>


## IoT (IFTTT)
<HR>

<span id="remarks">* For the setting of IFTTT, please refer to “Chapter 4: Cloud Control micro:bit by IFTTT”</span><BR><P>

<span id="subtitle">Step 1. Create applet in IFTTT</span><BR><P>
![auto_fit](images/Case10/Case10_ifttt1.png)<P>


## Result
<HR>

The micro:bit is controlled by IFTTT (trigger by date&time). The LED light will be turned on at 6pm and turned off at 6am every day.<BR><P>
![auto_fit](images/Case10/Case10_result.png)<P>


## Think
<HR>

Q1. How to turn on the light automatically if the today’s weather is cloudy reported by IFTTT.
