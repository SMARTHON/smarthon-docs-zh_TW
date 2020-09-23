# Chapter 4: Control your micro:bit by IFTTT Services

In this chapter, you will learn how to use trigger (other services) to implement action (micro:bit) by IFTTT. Below are the commonly used examples of services that can trigger micro:bit in IFTTT. <BR><P>
![auto_fit](images/Ch4/Ch4_des1.png)<P>
 
## Examples of services used in IFTTT
<HR>

With connection with different services in IFTTT, you can design your own applet with micro:bit projects using “if this then that (micro:bit)”. <BR><P>
![auto_fit](images/Ch4/Ch4_des2.png)<P>
You can tailor-make your own micro:bit projects by connecting Smarthon IoT (micro:bit) to over hundreds of services in cloud (IFTTT)! Create your IFTTT applet by choosing “If THIS then THAT”.<BR><P>
![auto_fit](images/Ch4/Ch4_des3.png)<P>

## Know the API (control command)
<HR>

[http://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand](http://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand)

## Hardware connect
<HR>

Connect LED to P0<BR><P>
 ![auto_fit](images/Ch4/Ch4_hardware.png)<P>


## Programming (Makecode), get the Device ID
<HR>

Goal: The below example is to turn on the light at 6 pm every day.<BR><P>

<span id="subtitle" >Step 1</span><BR><P>
After initializing, you can connect to the WiFi:<BR><P>
Choose IoT:bit -> Set Wi-Fi to ssid “”, pwd “”. Enter your Wi-Fi name and password<BR><P>
![auto_fit](images/Ch4/Ch4_p1.png)<P>

<span id="subtitle" >Step 2</span><BR><P>
“On WiFi connected” is an event handler.<BR><P>
It will be triggered once after connected with WiFi.<BR><P>
![auto_fit](images/Ch4/Ch4_p2.png)<P>


<span id="subtitle" >Step 3</span><BR><P>
Set the Wi-Fi listening on Micro:bit WAN control command action<BR><P>
After micro:bit connected to WiFi, it will start WiFi remote control (WAN)<BR><P>
If Wan command “Pin_On” is received, white LED will be turned on (intensity:1023)<BR><P>
![auto_fit](images/Ch4/Ch4_p3.png)<P>
 

<span id="subtitle" >Step 4</span><BR><P>
Get micro:bit Device ID
Load the program to the micro:bit and connect the micro:bit to the IoT:bit.<BR><P>
![auto_fit](images/Ch4/Ch4_p4.png)<P>
Wi-Fi IoT:bit will start to connect to internet, when the connection is successful, the IP Address would be shown. <BR><P>
![auto_fit](images/Ch4/Ch4_p5.png)<P>
Then, it will start WAN remote control. If the connection is successful, the Device ID would be shown. <BR><P>
Remember the Device ID, it will be used for WAN connection on the next step.<BR><P>
 ![auto_fit](images/Ch4/Ch4_p6.png)<P>


## Create your own applet to control micro:bit in IFTTT
<HR>

<span id="subtitle" >Step 1</span><BR><P>
Open your browser  , go to [https://ifttt.com/](https://ifttt.com/). Register your IFTTT account and once completed, log in to your IFTTT account.<BR><P>
![auto_fit](images/Ch4/Ch4_ifttt1.png)<P>


<span id="subtitle" >Step 2</span><BR><P>
On the top right menu, click “Create” > “Applets”<BR><P>
![auto_fit](images/Ch4/Ch4_ifttt2.png)<P>

<span id="subtitle" >Step 3</span><BR><P>
Create a trigger for the applet<BR><P>
* Select “This” > Choose service “Date & Time”
* Choose trigger “Every day at” 
* Select the time (e.g. 06PM, 00 Minutes; it means every day at 6pm) and click “Create trigger”.
![auto_fit](images/Ch4/Ch4_ifttt3.png)<P>


<span id="subtitle" >Step 4</span><BR><P>
Create an action for the applet
* Select “That”, choose action service “Smarthon”
* Choose action “Control Command”
* Input your Device ID (e.g.0xa3240ac45916) and control command (e.g. Pin_On). Then click “Create action”.
![auto_fit](images/Ch4/Ch4_ifttt4.png)<P>

<span id="subtitle" >Step 5</span><BR><P>
Review your applet, then click “Finish ”. <BR><P>

<span id="subtitle" >Step 6</span><BR><P>
After, the applet connection has been created it will show “connected”. <BR><P>
The light will be turned on at 6pm every day!<BR><P>
![auto_fit](images/Ch4/Ch4_ifttt5.png)<P>


## Result
<HR>

* After connected to WAN remote control, micro:bit will keep listening to the WAN command
* Every day at 6pm, clock will trigger IFTTT to send out micro:bit WAN command “Pin_On”
* The LED on P0 will be turned on.
![auto_fit](images/Ch4/Ch4_result.png)<P>



## Know more (Using WAN command with value in IFTTT)
<HR>

The above example is used to give on/off command only. What if we want to pass values to the micro:bit (e.g. control the LED intensity)? Below is an example of using control command with value.<BR><P>

### Know the API (control command with value)
<HR>

[http://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand&value=Value](http://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand&value=Value) 

### Programming (Makecode), get the Device ID
<HR>

<span id="subtitle" >Step 1</span><BR><P>
Set the Wi-Fi listening on micro:bit WAN control command action<BR><P>
* Initialize IoT:bit and OLED, the micro:bit start connecting Wifi.
![auto_fit](images/Ch4/Ch4_2_p1.png)<P>
![auto_fit](images/Ch4/Ch4_2_p2.png)<P>
![auto_fit](images/Ch4/Ch4_2_p3.png)<P>

The LED intensity on P0 can be changed by a WAN command received with value:<BR><P>
* Device ID: a unique ID (to identify micro:bit device to receive the command)
* WAN_Command: PinValue (command for micro:bit)
* Value: the intensity of the LED (the value for the command)



<span id="subtitle" >Step 2</span><BR><P>
Get micro:bit Device ID<BR><P>
* Connect micro:bit to internet, IP address would be shown.
![auto_fit](images/Ch4/Ch4_2_p5.png)<P>
* Then, it will start WAN remote control. If the connection is successful, the Device ID would be shown. 
* Remember the Device ID, it will be used for WAN connection on the next step.
![auto_fit](images/Ch4/Ch4_2_p6.png)<P>


### Create your own applet to control micro:bit in IFTTT
<HR>

<span id="subtitle" >Step 1</span><BR><P>
You can send WAN command with value in IFTTT. In this example, click “That” to select the action<BR><P>
![auto_fit](images/Ch4/Ch4_2_ifttt1.png)<P>

        
<span id="subtitle" >Step 2</span><BR><P>
Create an action for the applet
* Select “That”, choose action service “Smarthon”
* Choose action “Control Command (with value)”
* Input your Device ID (e.g. 0xfa240ac45917), control command (e.g. PinValue) and Value (e.g. 600). Then click “Create action”.
![auto_fit](images/Ch4/Ch4_2_ifttt2.png)<P>
 
 

<span id="subtitle" >Step 3</span><BR><P>
Review your applet, then click “Finish ”. <BR><P>


<span id="subtitle" >Step 4</span><BR><P>
After, the applet connection has been created it will show “connected”. <BR><P>
The light will be turned on at 6pm every day!<BR><P>
![auto_fit](images/Ch4/Ch4_2_ifttt3.png)<P>

### Result
<HR>

* After connected to WAN remote control, micro:bit will keep listening to the WAN command
* Every day at 6pm, clock will trigger IFTTT to send out micro:bit WAN command “PinValue” (with value “600”)
* The LED on P0 will be turned on (with light intensity: 600).
![auto_fit](images/Ch4/Ch4_2_result.png)<P>