# Chapter 3: Control micro:bit by App Inventor 2

App inventor 2 is a blocks-based programming tool, which help beginners to build fully functional app in Android device. The interface is graphical base and support drag and drop operations. It consists of different components, such as button, slider, date pickers, image, camera, sensors including Accelerometer and connectivity to web, etc. The app can be exported or published to Play store for our daily life.<BR><P>
For creating IoT application, you can use App Inventor 2 to create web connection with micro:bit. In WAN control, after micro:bit is connected to internet, it keep listening and execute customized operation when WAN command is received. The customized operation could be Pin On/off, such as “open/close LED”, or set value such as “set the light intensity” and “set current time”.<BR><P>
![auto_fit](images/Ch3/Ch3_des1.png)<P>
In the following example, PC/mobile and micro:bit are connected to LAN network through WAN<BR><P>
PC/mobile will send a control command to micro:bit. When the micro:bit receive the command, it will turn on/off the module on the pin.<BR><P>
![auto_fit](images/Ch3/Ch3_des2.png)<P>
<span id="remarks" >*Before we control the micro:bit, please make sure your micro:bit is connected to the Wi-Fi.</span>

## Know the API (control command)
<HR>

[http://control.smarthon.cc/publish?id=DeviceID&msg=ControlComman](http://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand) 

## Hardware connect
<HR>

Connect LED to P0
![auto_fit](images/Ch3/Ch3_hardware.png)<P>

## Programming (Makecode), get the Device ID
<HR>

Goal: This example is to turn on/off micro:bit modules only.<BR><P>

<span id="subtitle" >Step 1</span><BR><P>
After initializing, you can connect to the WiFi:<BR><P>
Choose IoT:bit -> Set Wi-Fi to ssid “”, pwd “”. Enter your Wi-Fi name and password<BR><P>
![auto_fit](images/Ch3/Ch3_p1.png)<P>

<span id="subtitle" >Step 2</span><BR><P>
“On WiFi connected” is an event handler.<BR><P>
It will be triggered once after connected with WiFi.<BR><P>
![auto_fit](images/Ch3/Ch3_p2.png)<P>

<span id="subtitle" >Step 3</span><BR><P>
Set the Wi-Fi listening on Micro:bit WAN control command action<BR><P>
After micro:bit connected to WiFi, it will start WiFi remote control (WAN)<BR><P>
If Wan command “Pin_On” is received, white LED will be turned on (intensity:1023)<BR><P>
If Wan command “Pin_Off” is received, white LED will be turned off (intensity:0)<BR><P>
![auto_fit](images/Ch3/Ch3_p3.png)<P>

<span id="subtitle" >Step 4: Get micro:bit Device ID</span><BR><P>

Load the program to the micro:bit and connect the micro:bit to the IoT:bit.<BR><P>
![auto_fit](images/Ch3/Ch3_p4.png)<P>
Wi-Fi IoT:bit will start to connect to internet, when the connection is successful, the IP Address would be shown. <BR><P>
![auto_fit](images/Ch3/Ch3_p5.png)<P>
Then, it will start WAN remote control. If the connection is successful, the Device ID would be shown. <BR><P>
Remember the Device ID, it will be used for WAN connection on the next step.<BR><P>
![auto_fit](images/Ch3/Ch3_p6.png)<P>

## Create the mobile app in App Inventor 2
<HR>

<span id="subtitle" >Step 1: Create a new project in App Inventor 2, on “Designer”</span><BR><P>
Drag “Layout”>”HorizontalArragement” to the page. <BR><P>
Drag “User Interface” > “Button” twice to the place inside the HorizontalArrangement<BR><P>
Drag Connectivity> “Web” to the page <BR><P>
![auto_fit](images/Ch3/Ch3_app1.png)<P>

<span id="subtitle" >Step 2: Get WAN control URL (command without value)</span><BR><P>
The WAN control command URL is:<BR><P>
[http://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand](http://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand)

<span id="subtitle" >Step 3: In App Inventor 2, on “Blocks”</span><BR><P>
When “Button1” is clicked, it direct to the command URL, and control the micro:bit by Wi-Fi (WAN connection). <BR><P>
a. Device ID: a unique ID (to identify micro:bit device to receive the command)<BR><P>
b. WAN command: Pin_On<BR><P>
![auto_fit](images/Ch3/Ch3_app2a.png)<P>
<BR>
When “Button2” is clicked, it direct to the command URL, and control the micro:bit by Wi-Fi (WAN connection).<BR><P> 
a. Device ID: a uniquie ID (to identify the micro:bit which receive the command)<BR><P>
b. WAN command: Pin_Off<BR><P>
![auto_fit](images/Ch3/Ch3_app2b.png)<P>

## Result
<HR>

In App Inventor 2, you can perform real-time testing in your mobile phone by AI Companion<BR><P>
App Inventor 2 	Mobile phone (by AI Companion)<BR><P>
![auto_fit](images/Ch3/Ch3_app3.png)<P>
Also, you can also build and download the android app and open it in your mobile phone.<BR><P>
App Inventor 2 	Mobile phone (by building app)<BR><P>
![auto_fit](images/Ch3/Ch3_app4.png)<P>


<span id="subtitle" >Testing 1:</span><BR><P>
After connected to WAN remote control is started, when Button1 is clicked, it will send WAN command “Pin_On” to the micro:bit with provided Device ID.<BR><P>
The LED on P0 will be turned on.<BR><P>
![auto_fit](images/Ch3/Ch3_result1.png)<P>
<span id="subtitle" >Testing 2:</span><BR><P>
After connected to WAN remote control is started, when Button2 is clicked, it will send WAN command “Pin_Off” to the micro:bit with provided Device ID.<BR><P>
The LED on P0 will be turned off.<BR><P>
![auto_fit](images/Ch3/Ch3_result2.png)<P>

## Know more (with value)
<HR>

The above example is for turning the LED on/off only. How about if we want to control the LED with intensity? The below example is to control your modules with intensity.<BR><P>


## Know the API (control command with value)
<HR>

[http://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand&value=Value](http://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand&value=Value)

## Hardware connect
<HR>

Connect LED to P0<BR><P>
![auto_fit](images/Ch3/Ch3_hardware.png)<P>

## Programming (Makecode)
<HR>

<span id="subtitle" >Step 1</span><BR><P>
Set the Wi-Fi listening on micro:bit WAN control command action<BR><P>
Initialize IoT:bit and OLED, the micro:bit start connecting Wifi.<BR><P>
![auto_fit](images/Ch3/Ch3_p2_1.png)<P>
![auto_fit](images/Ch3/Ch3_p2_2.png)<P>
![auto_fit](images/Ch3/Ch3_p2_3.png)<P>
The LED intensity on P0 can be changed by a WAN command received with value:<BR><P>
a. Device ID: a unique ID (to identify micro:bit device to receive the command)<BR><P>
b. WAN_Command: PinValue (command for micro:bit)<BR><P>
c. Value: the intensity of the LED (the value for the command) <BR><P>

<span id="subtitle" >Step 2: Get micro:bit Device ID</span><BR><P>

Load the program to the micro:bit and connect the micro:bit to the IoT:bit.<BR><P>
![auto_fit](images/Ch3/Ch3_p2_4.png)<P>
Wi-Fi IoT:bit will start to connect to internet, when the connection is successful, the IP Address would be shown. <BR><P>
![auto_fit](images/Ch3/Ch3_p2_5.png)<P>
Then, it will start WAN remote control. If the connection is successful, the Device ID would be shown. <BR><P>
Remember the Device ID, it will be used for WAN connection on the next step.<BR><P>
![auto_fit](images/Ch3/Ch3_p2_6.png)<P>


## App Inventor 2 setting
<HR>

In below example, you can create a web connection, set the URL to the control command URL in App inventor.<BR><P>
<span id="subtitle" >Step 1</span><BR><P>
Create a new project in App Inventor 2, on “Designer”. <BR><P>
Drag “Layout”>”HorizontalArragement” to the page. <BR><P>
Drag “User Interface” > “TextBox” to the place inside the HorizontalArrangement<BR><P>
Drag “User Interface” > “Button” to the place inside the HorizontalArrangement<BR><P>
Drag Connectivity> “Web” to the page <BR><P>
![auto_fit](images/Ch3/Ch3_app2_1.png)<P>

<span id="subtitle" >Step 2</span><BR><P>
Get WAN control URL (command with value)<BR><P>

The WAN control command URL is:<BR><P>
[http://control.smarthon.cc/publish?id=0xfa240ac45917&msg=PinValue&value=600](http://control.smarthon.cc/publish?id=0xfa240ac45917&msg=PinValue&value=600)

<span id="subtitle" >Step 3</span><BR><P>

On “Blocks” <BR><P>
When “Button3” is clicked, it direct to the command URL, and control the micro:bit by Wi-Fi (WAN connection). <BR><P>
a. Device ID: a unique ID (to identify micro:bit device to receive the command)<BR><P>
b. WAN command: PinValue<BR><P>
c. Value: TextBox1.Text (refer to the input value)<BR><P>
![auto_fit](images/Ch3/Ch3_app2_2.png)<P>

## Result
<HR>

In App Inventor 2, you can perform real-time testing in your mobile phone by AI Companion<BR><P>
App Inventor 2 	Mobile phone (by AI Companion)<BR><P>
![auto_fit](images/Ch3/Ch3_app2_3.png)<P>
Also, you can also build and download the android app and open it in your mobile phone.<BR><P>
App Inventor 2 	Mobile phone (by building the app)<BR><P>
![auto_fit](images/Ch3/Ch3_app2_4.png)<P>

<span id="subtitle" >Testing 1:</span><BR><P>
After connected to WAN remote control is started, when Button3 is clicked, it will send WAN command “PinValue” with value “600” to the micro:bit with provided Device ID.<BR><P>
The LED on P0 will be turned on (with intensity: 600)<BR><P>
![auto_fit](images/Ch3/Ch3_result2_1.png)<P>
<span id="subtitle" >Testing 2:</span><BR><P>
when Button3 is clicked, it will send WAN command “PinValue” with value “0” to the micro:bit with provided Device ID.<BR><P>
The LED on P0 will be turned off (with intensity: 0)<BR><P>
![auto_fit](images/Ch3/Ch3_result2_2.png)<P>
