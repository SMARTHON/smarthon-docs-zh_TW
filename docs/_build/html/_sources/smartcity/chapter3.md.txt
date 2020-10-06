# Chapter 3: Control micro:bit by App Inventor 2

App inventor 2 is a blocks-based programming tool, which help beginners to build fully functional app in Android device. The interface is graphical base and support drag and drop operations. It consists of different components, such as button, slider, date pickers, image, camera, sensors including Accelerometer and connectivity to web, etc. The app can be exported or published to Play store for our daily life.<BR><P>
![auto_fit](images/Ch3/Ch3_des1.png)<P>
For creating IoT application, you can use App Inventor 2 to create web connection with micro:bit. In WAN control, after micro:bit is connected to internet, it keep listening and execute customized operation when WAN command is received. The customized operation could be Pin On/off, such as “open/close LED”, or set value such as “set the light intensity” and “set current time”.<BR><P>
![auto_fit](images/Ch3/Ch3_des2.png)<P>


## Know the API (Control command)
<HR>

API is one way to communicate between the objects on the Internet world. API is just like an “URL” which is website link.<BR><P>
![auto_fit](images/Ch3/Ch3_des3.png)<P>
This is the API you can use to control the micro:bit<BR><P>
http://control.smarthon.cc/publish?id=`DeviceID`&msg=`ControlCommand`

## Hardware connect
<HR>

Connect LED to P0<BR><P>
![auto_fit](images/Ch3/Ch3_hardware.png)<P>
 
## Programming (Makecode), get the Device ID
<HR>

Goal: This example is to turn on/off micro:bit modules only.<BR><P>

<span id="subtitle">Step 1</span><BR><P>
After initializing, you can connect to the WiFi:<BR><P>
Choose `IoT:bit` -> `Set Wi-Fi to ssid “”, pwd “”`. Enter your Wi-Fi name and password<BR><P>
![auto_fit](images/Ch3/Ch3_p1.png)<P>

<span id="subtitle">Step 2</span><BR><P>
`On WiFi connected` is an event handler.<BR><P>
It will be triggered once after connected with WiFi.<BR><P>
![auto_fit](images/Ch3/Ch3_p2.png)<P>

<span id="subtitle">Step 3: Set the Wi-Fi listening on Micro:bit WAN control command action</span><BR><P>
After micro:bit connected to WiFi, it will start WiFi remote control (WAN).<BR><P>
* If Wan command “Pin_On” is received, white LED will be turned on (intensity:1023)
* If Wan command “Pin_Off” is received, white LED will be turned off (intensity:0)
![auto_fit](images/Ch3/Ch3_p3.png)<P>

<span id="subtitle">Step 4: Get micro:bit Device ID</span><BR><P>
After the micro:bit is connected to Wi-Fi successfully, it will start WAN control. The device ID will be shown.<BR><P>
![auto_fit](images/Ch3/Ch3_p4.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_923eWocsr17q](https://makecode.microbit.org/#pub:_923eWocsr17q)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_923eWocsr17q" width="100%" height="500" frameborder="0"></iframe>


## Create the mobile app in App Inventor 2
<HR>

<span id="subtitle">Step 1</span><BR><P>
Create a new project in App Inventor 2, on “Designer”<BR><P>
1. Drag “Layout”>”HorizontalArragement” to the page. 
2. Drag “User Interface” > “Button” twice to the place inside the HorizontalArrangement
3. Drag Connectivity> “Web” to the page 
![auto_fit](images/Ch3/Ch3_app1.png)<P>
    
<span id="subtitle">Step 2</span><BR><P>
Set the program in app inventor 2, on “Blocks” <BR><P>
* Take the block as below
![auto_fit](images/Ch3/Ch3_app2.png)<P>
* When Button 1 and 2 is pressed, it calls the WAN control API respectively
* http://control.smarthon.cc/publish?id=`DeviceID`&msg=`ControlCommand`
![auto_fit](images/Ch3/Ch3_app3.png)<P>
 

## Result
<HR>

In App Inventor 2, you can perform real-time testing in your mobile phone by AI Companion<BR><P>
App Inventor 2 	Mobile phone (by AI Companion)<BR><P>
![auto_fit](images/Ch3/Ch3_result1.png)<P>

Also, you can also build and download the android app and open it in your mobile phone.<BR><P>
App Inventor 2 	Mobile phone (by building app)<BR><P>
![auto_fit](images/Ch3/Ch3_result2.png)<P>

<span id="subtitle">Testing:</span><BR><P>
After the WAN remote control is started, <BR><P>
* When Button1 is clicked, it will send WAN command “Pin_On” to the micro:bit with provided Device ID, the LED on P0 will be turned on.
![auto_fit](images/Ch3/Ch3_testing1.png)<P>
* When Button2 is clicked, it will send WAN command “Pin_Off” to the micro:bit with provided Device ID, the LED on P0 will be turned off.
![auto_fit](images/Ch3/Ch3_testing2.png)<P>

## Know more (Using WAN command with value in App Inventor 2)
<HR>

The above example is for turning the LED on/off only. How about if we want to control the LED with intensity? The below example is to control your modules with intensity.<BR><P>

### Know the API (control command with value)
<HR>


1. http://control.smarthon.cc/publish?id=`DeviceID`&msg=`ControlCommand` <BR><P>

2. http://control.smarthon.cc/publish?id=`DeviceID`&msg=`ControlCommand`&value=`Value` <BR><P>


### Programming (Makecode)
<HR>

Similarly, initialize the Wi-Fi and connect wifi on start. For this turn, we will use “On WAN command received with value WAN_Command Value”<BR><P>
![auto_fit](images/Ch3/Ch3_2_p1.png)<P>
If Wan command “PinValue” is received, white LED will be turned on with the given intensity. <BR><P>
![auto_fit](images/Ch3/Ch3_2_p2.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_8sbfHLTTvReE](https://makecode.microbit.org/#pub:_8sbfHLTTvReE)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_8sbfHLTTvReE" width="100%" height="500" frameborder="0"></iframe>


### App Inventor 2 setting
<HR>

<span id="subtitle">Step 1</span><BR><P>
Create a new project in App Inventor 2, on “Designer”. <BR><P>
1. Drag “Layout” > ”HorizontalArragement” to the page. 
2. Drag “User Interface” > “TextBox” and “Button” to the place inside the HorizontalArrangement
3. Drag “Connectivity” > “Web” to the page 
![auto_fit](images/Ch3/Ch3_2_app1.png)<P>

<span id="subtitle">Step 2</span><BR><P>
When Button 3 is pressed, it calls the WAN control API respectively<BR><P>
* http://control.smarthon.cc/publish?id=`0xfa240ac45917`&msg=`PinValue`&value=`600` 
![auto_fit](images/Ch3/Ch3_2_app2.png)<P>

 
### Testing
<HR>

When the button 3 is pressed with the intensity of 0 or 600, it will be turned on accordingly.<BR><P>
![auto_fit](images/Ch3/Ch3_2_testing.png)<P>