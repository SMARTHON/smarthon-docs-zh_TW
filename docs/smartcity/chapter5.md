# Chapter 5: Object to Object communication

In this example, micro:bit (sender and receiver) are connected to a channel called “chatroom”.<BR><P>
Peter want to send a smile message to Sally via internet (WAN). Peter’s micro:bit will send a Wi-Fi message “smile” to Sally’s micro:bit. When Sally receive a WiFi message smile, her micro:bit LED will show a smile icon.<BR><P>
![auto_fit](images/Ch5/Ch5_des.png)<P>

<span id="remarks">*Before we control the micro:bit, please make sure your micro:bit is connected to the Wi-Fi.</span><BR><P>



 
## Set the channel name (Receiver)

<span id="subtitle">Step 1</span><BR><P>
After initializing, you can connect to the WiFi:<BR><P>
Choose `IoT:bit` -> `Set Wi-Fi to ssid “”, pwd “”`. Enter your Wi-Fi name and password<BR><P>
![auto_fit](images/Ch5/Ch5_p1.png)<P>

<span id="subtitle">Step 2</span><BR><P>
`On WiFi connected` is an event handler.<BR><P>
It will be triggered once after connected with WiFi.<BR><P>
![auto_fit](images/Ch5/Ch5_p2.png)<P>


<span id="subtitle">Step 3</span><BR><P>
When Wifi is connected, it start WiFi Listening in channel “chatroom” <BR><P>
<span id="remarks">(sender and receiver must be in the same channel)</span><BR><P>
* When it receive a WiFi message called “smile”, the LED will show a smile icon; 
* when it receive a WiFi message called “sad”, the LED will show a sad icon.
![auto_fit](images/Ch5/Ch5_p3.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_boM473hYHeVw](https://makecode.microbit.org/#pub:_boM473hYHeVw)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_boM473hYHeVw" width="100%" height="500" frameborder="0"></iframe>


## Send Wi-Fi message in a channel (Sender)

<span id="subtitle">Step 1</span><BR><P>
After initializing, you can connect to the WiFi:<BR><P>
Choose `IoT:bit` -> `Set Wi-Fi to ssid “”, pwd “”`. Enter your Wi-Fi name and password<BR><P>
![auto_fit](images/Ch5/Ch5_p4.png)<P>

<span id="subtitle">Step 2</span><BR><P>
After WiFi is connected, we can press button A / button B to send WiFi message<BR><P>
<span id="remarks">(the channel name of the sender and receiver must be the same)</span><BR><P>
* Button A: send a WiFi message “smile” to channel “chatroom” 
* Button B:  send a WiFi message “sad” to channel “chatroom” 
![auto_fit](images/Ch5/Ch5_p5.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_2pWTEyLWqFDu](https://makecode.microbit.org/#pub:_2pWTEyLWqFDu)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_2pWTEyLWqFDu" width="100%" height="500" frameborder="0"></iframe>


## Result

### Sender
After connected to WiFi, IP address would be shown.<BR><P>
Pressed “A” button, it will send WiFi message “smile” in channel “chatroom”. <BR><P>
![auto_fit](images/Ch5/Ch5_result1.png)<P>
 
Pressed “B” button, it will send WiFi message “sad” in channel “chatroom”. <BR><P>
![auto_fit](images/Ch5/Ch5_result2.png)<P>


### Receiver
After connected to WiFi, IP it will start listening in channel “chatroom”. When connected successfully, Channel name “chatroom” will be shown.<BR><P>
![auto_fit](images/Ch5/Ch5_result3.png)<P>
* When WiFi message “smile” is received, OLED will show “WIFI msg: smile”. Micro:bit will show an smile icon: ![icon](images/Ch5/smile.png)
![auto_fit](images/Ch5/Ch5_result4.png)<P>
* When WiFi message “sad” is received, OLED will show “WIFI msg: smile”. LED will show a sad icon: ![icon](images/Ch5/sad.png)
![auto_fit](images/Ch5/Ch5_result5.png)<P>

