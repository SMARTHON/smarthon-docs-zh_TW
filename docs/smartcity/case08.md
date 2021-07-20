# IoT Case 08: Automated Traffic Light

Level: ![level](images/level5.png)

<span id="remarks">* For more details, please refer to “Chapter 5: Object to Object communication”</span>
![auto_fit](images/Case8/case-08_1.png)<P>

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
![auto_fit](images/Case8/Concept-diagram-Case8_sender.png)<P>

### Part List
<HR>

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

<span id="subtitle">Step 1. Initialize OLED and IoT:bit and connect to WiFi</span><P>
* Snap `Initialize OLED with width:128, height: 64` to `on start`
* Snap `Initialize IoT:bit TX P16 RX P8` from `IoT:bit` to `on start`
* Snap `Set Wi-Fi to ssid pwd` from `IoT:bit`
* Enter your Wi-Fi name and password. Here we set `smarthon` as `SSID` and `12345678` as `password`
* Set variable `light2` to 0 from `variables` 
![auto_fit](images/Case8/Case8a_p1.png)<P>

<span id="subtitle">Step 2. Show icon “tick” after WiFi connection</span><P>
* Snap `show icon` from `basic` to `On WiFi connected` and select icon `tick`
![pic_60](images/Case8/Case8a_p2.png)<P>

<span id="subtitle">Step 3. Check traffic status</span><P>
* Snap `if statement` to block `forever`
* If `WiFi is connected`,
* Set `variable2` to `light value from light sensor at P0`
* Snap `clear OLED display` from `OLED` to avoid overlap
* Snap `show string` and show value of variables `light2`
* `Pause` 6000 (ms) to another checking
![auto_fit](images/Case8/Case8a_p3.png)<P>

<span id="subtitle">Step 4. Send notification when someone pass by</span><P>
* Snap `if statement` 
* Set `light` < `10` in to if-condition (traffic jam is detected)
* Snap `WiFi Sender send channel… message…` from `IoT:bit` > `channel`
* Set channel to `tsuenwan`, message `trafficjam`
* Set `else-condition` (traffic jam is not detected)
* Snap `WiFi Sender send channel… message…` from `IoT:bit` > `channel`
* Set channel to `tsuenwan`, message `nojam`
![auto_fit](images/Case8/Case8a_p4.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_P5fAujhip5Lh](https://makecode.microbit.org/_P5fAujhip5Lh)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_P5fAujhip5Lh" width="100%" height="500" frameborder="0"></iframe>


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
![auto_fit](images/Case8/Concept-diagram-Case8_receiver.png)<P>

### Part List
<HR>

![auto_fit](images/Case8/Case8b_parts.png)<P>

### Assembly step
<HR>

<span id="subtitle">Step 1</span><P>
Attach the Traffic light Module to G1 model using M4 screw and nut. Put together all the cardboard parts (G1-G2)<BR><P>
![auto_fit](images/Case8/Case8b_ass1.png)<P>

<span id="subtitle">Step 2</span><P>
Assembly completed!<BR><P>
![auto_fit](images/Case8/Case8b_ass2.png)<P>


### Hardware connect
<HR>

Connect the Traffic LED Module to P0 port of IoT:bit<BR><P>
![auto_fit](images/Case8/Case8b_hardware.png)<P>


### Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize OLED and IoT:bit and connect to WiFi</span><P>
* Snap `Initialize OLED with width:128, height: 64` to `on start`
* Snap `Initialize IoT:bit TX P16 RX P8` from `IoT:bit` to `on start`
* Snap `Set Wi-Fi to ssid pwd` from `IoT:bit`
* Enter your Wi-Fi name and password. Here we set `smarthon` as `SSID` and `12345678` as `password`
* Set variable `oldmsg` to “” from `variables` 
![auto_fit](images/Case8/Case8b_p1.png)<P>

<span id="subtitle">Step 2. Join Channel “tsuenwan”</span><P>
* Snap `show icon` from `basic` to `On WiFi connected` and select icon `tick`
* Snap `WiFi Receiver join channel` from `IoT` > `Chanel`
* Set channel name `tsuenwan`
![auto_fit](images/Case8/Case8b_p2.png)<P>

<span id="subtitle">Step 3. Receive WiFi message</span><P>
* Snap `On WiFi Receiver received`
* Go to OLED
* Snap the `clear OLED display` to `On WiFi received` to avoid overlap
* Snap the `show string` 
* Draw variable `receivedMessage` to show string placeholder
![pic_70](images/Case8/Case8b_p3.png)<P>
 
<span id="subtitle">Step 4. Set up a new function (TurnRed)</span><P>
* `Control traffic light at P1` green on from `SmartCity` > `Output`
* `Pause` for 2000ms from basic
* `Control traffic light at P1` yellow on, `pause` for 2000ms
* `Control traffic light at P1` red on and `pause` for 2000ms.
![auto_fit](images/Case8/Case8b_p4.png)<P>

<span id="subtitle">Step 5. Set up a new function (TurnGreen)</span><P>
* `Control traffic light at P1` red on from `SmartCity` > `Output`
* `Pause` for 2000ms from basic
* `Control traffic light at P1` red and yellow on, `pause` for 2000ms
* `Control traffic light at P1` green on and `pause` for 2000ms.
![auto_fit](images/Case8/Case8b_p5.png)<P>

<span id="subtitle">Step 6. Set traffic light default status</span><P>
* Insert function `TurnGreen` to `on start`
![pic_60](images/Case8/Case8b_p6.png)<P>

<span id="subtitle">Step 7. Change traffic light status</span><P>
* Snap `if-statement`, set `received Message` ≠ `oldmsg` to `if-condition`
* Set `oldmsg` = `receivedMessage` (renew the latest traffic status)
* Snap another `if-statement` 
* Set `receivedMessage` = `trafficjam` to `if-condition`
* Call function `TurnRed`
* Set `receivedMessage` = `nojam` to `else-if-condition`
* Call function `TurnGreen`
![auto_fit](images/Case8/Case8b_p7.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_V5jcy5Pvm7hF](https://makecode.microbit.org/_V5jcy5Pvm7hF)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_V5jcy5Pvm7hF" width="100%" height="500" frameborder="0"></iframe>


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
