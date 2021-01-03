# Chapter 3: Direct Control micro:bit by App Inventor 2

## Introduction

App inventor 2 is a blocks-based programming tool, which help beginners to build fully functional app in Android device. The interface is graphical base and support drag and drop operations. It consists of different components, such as button, slider, date pickers, image, camera, sensors including Accelerometer and connectivity to web, etc. The app can be exported or published to Play store for our daily life.<BR><P>

![auto_fit](images/Ch3/Ch3_des1.png)<P>
For creating IoT application, you can use App Inventor 2 to create web connection with micro:bit. In WAN control, after micro:bit is connected to internet, it keep listening and execute customized operation when WAN command is received. The customized operation could be Pin On/off, such as “open/close LED”, or set value such as “set the light intensity” and “set current time”.<BR><P>

![auto_fit](images/Ch3/Ch3_des2.png)<P>


## Know the API (control command)
<HR>

What is API? API is one way to communicate between the objects in the Internet world. API is just like an “URL” which is website link. <P>
In App inventor, we use “API” to communicate with micro:bit. Normally, we need to know the (1) device ID (2) the message need to be sent to the micro:bit and optionally (3) value if needed.

![auto_fit](images/Ch3/Ch3_des3.png)
<P>

<B><u>(1) Basic API:</u></B>
```
https://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand
```
`id`: The unique ID of device, used to identify the target .<BR>
`msg`: The command needs to send.<P>
Example: "https://control.smarthon.cc/publish?id=0x123456781&msg=lighton". 
In this case, we send the msg command “lighton” to device id “0x123456781”.<P>


<B><u>(2) Advanced API:</u></B>
```
https://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand&value=Value
```

`id`: The unique ID of device, used to identify the target .<BR>
`msg`: The command needs to send.<BR>
`value`(optional): Used when need for the command.<P>
Example: "https://control.smarthon.cc/publish?id=0x123456781&msg=lighton&value=500" .
In this case, we send the msg command “lighton” with intensity value "500" to device id “0x123456781”.<P>

 
## Scenario Example
<HR>
<span id="subtitle">Goal:</span><P>

This example is to turn on/off micro:bit LED by using app inventor 2.<BR>

<span id="subtitle">Description: </span><P>

In this example, there are 2 parts involved. <P>

* In part 1, we need to connect the micro:bit to the internet and get the device ID. 
* In part 2, design the mobile app and set the API with the device ID from part 1.

<P>

![auto_fit](images/Ch3/Ch3_des4.png)<P>
 
 
## Part 1: Coding
<HR>

<span id="subtitle">Goal:</span><P>
We need to get the Device ID and set the corresponding action.<BR><P>

<span id="subtitle">Connection Diagram:</span><br>
* Connect LED to P0<BR>

![auto_fit](images/Ch3/Ch3_hardware.png)<P>


<span id="subtitle">Step 1: Connect WiFI</span><BR><P>
Before we try to use WiFi Control function, we need to connect to the network, we have already know how to connect to the WiFi on the first chapter.
<BR><P>
![auto_fit](images/Ch3/Ch3_p1.png)<P>

<span id="subtitle">Step 2: Get Device ID</span><BR><P>
`On WiFi connected` is an event handler.
It will be triggered once after connected with WiFi.
The handler will provide the `Device ID` variable which used to identify and control the Microbit.<BR>
* Go to OLED Tab
* Snap `initialize OLED with width…height..` to `on start`
* Snap the `show string` inside the `On WiFi connected`
* Draw the `Device ID` variable from `On WiFi connected` to the `show tring` block placeholder

![auto_fit](images/Ch3/Ch3_p2.png)<P>

*If you worried about forget the `Device ID` during program running, you may access it by the variable under Control tab<P>
* Go to Control tab
* Snap the `Device ID` variable to the placeholder<P> 

![auto_fit](images/Ch3/Ch3_p2_1.png)<P>


<span id="subtitle">Step 3: Control with Command</span><BR><P>
After connected to the WiFI, the connection to the server will be done automatically, it is ready to receive command though network.
To get the command, we can use the `on Wi-Fi received` handler in WAN control tab.<BR>
* Snap the `on WiFi received` handler to stage
* Do the `if-condition statement` to the variable `WAN_Command`
* If `Wan_command` “Pin_On” is received, white LED will be turned on (intensity:1023)
* If `Wan_command` “Pin_Off” is received, white LED will be turned off (intensity:0)<BR>

Attention: Please be aware that the **P** is in capital letter.
<P>

![auto_fit](images/Ch3/Ch3_p3.png)<P>

<span id="subtitle">Step 4: Show the Command</span><BR><P>
Sometimes you may need to show the recevied command for debugging, so if you need that, you can use the OLED `show string` to display the command on the OLED.
* Go to OLED
* Snap the `clear OLED display` to `On WiFi received` to avoid overlap 
* Snap the `show string` to `On WiFi received`
* Draw the `WAN_Command` variable to `show string` placeholder

![auto_fit](images/Ch3/Ch3_p3_1.png)<P>


<span id="subtitle"><u>Advanced Usage: Command with value</u></span><BR><P>
If you want to control the module with value, you can use the another block which contain `value` variable.<BR>
If `Wan command` “PinValue” is received, white LED will be turned on with the given intensity `value`. 
<BR>
You may also show the `WAN_Command` and `value` by `show string`.<P>
![auto_fit](images/Ch3/Ch3_p4.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_43A5eiHmjTMH](https://makecode.microbit.org/#pub:_43A5eiHmjTMH)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_43A5eiHmjTMH" width="100%" height="500" frameborder="0"></iframe><P>


## Part 2: App Inventor 2 configuration
<HR>

<H3>Goal:</H3>
We need to create mobile app to control the IoT:bit by using API. <P>

<span id="subtitle">Step 1: Create Layout</span><BR><P>
Create a new project in App Inventor 2, on “Designer”<BR>
* Drag “Layout”>”HorizontalArragement” to the page. 
* Drag “User Interface” > “Button” twice to the place inside the HorizontalArrangement
* Drag Connectivity> “Web” to the page 
![auto_fit](images/Ch3/Ch3_app1.png)<P>
    
<span id="subtitle">Step 2: Define Function</span><BR><P>
Set the program in app inventor 2, on “Blocks” <BR>
* Take the block as below
![auto_fit](images/Ch3/Ch3_app2.png)<P>
* When Button 1 and 2 is pressed, it calls the WAN control API respectively
http://control.smarthon.cc/publish?id=`DeviceID`&msg=`ControlCommand`

![auto_fit](images/Ch3/Ch3_app3.png)<P>
 
<H3><u>Advanced Usage: Control with value</u></H3>
If you want to control the module with value, you can create in textbox with the button let the user to input the value.<P>

<B>Layout:</B><BR>
![auto_fit](images/Ch3/Ch3_app3_1.png)<P>

<B>Programming:</B><P>
When Button 3 is pressed, it calls the WAN control API respectively
http://control.smarthon.cc/publish?id=`0xfa240ac45917`&msg=`PinValue`&value=`600`<BR>

![auto_fit](images/Ch3/Ch3_app3_2.png)<P>

<span id="subtitle">Step 3: Build the apps</span><BR><P>
Build and test the mobile app. <BR>
In App Inventor 2, you can perform real-time testing in your mobile phone by AI Companion<BR>

![auto_fit](images/Ch3/Ch3_app4.png)<P>

Also, you can also build and download the android app and open it in your mobile phone.<P>

![auto_fit](images/Ch3/Ch3_app4_1.png)<P>

## Result
<HR>

After the WiFI Connected, the Device ID will show<P>

![auto_fit](images/Ch3/Ch3_result1.png)<P>


<U><B>Normal Case:</B></U><BR>
When Button1 is clicked, it will send WAN command “Pin_On” to the micro:bit with provided Device ID, the LED on P0 will be turned on. When button 2 is clicked, the LED will be turned off.<P>

![auto_fit](images/Ch3/Ch3_result2.png)<P>

<U><B>Control the value(advanced):</B></U><BR>
When the button 3 is pressed with the intensity of 0 or 600, it will be turned on accordingly.<P>

![auto_fit](images/Ch3/Ch3_result3.png)<P>


