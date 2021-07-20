# Chapter 4: Cloud Control micro:bit by IFTTT

## Introduction
In this chapter, you will know how to control micro:bit from the IFTTT cloud. Once there are some changes on Internet services like weather, time or different connected devices like voice assistant and some smart home device, you can send the command to micro:bit to do the action. <BR><P>

![auto_fit](images/Ch4/Ch4_2_intro.png)<P>

In practice, the below example you may apply for:
* Turn the street light on at 6pm and off after 6am everyday
* Turn on the water pump every day at 06:00 for 2 second
* If the forecast weather is rain, open the umbrella
* Use voice command to control robot actions
* When the door is closed, LED is turned on.


## Scenario Example
<HR>
<span id="subtitle">Goal:</span> <P>

The micro:bit is connected to the Internet. Once the time is changed to 6 pm, the IFTTT cloud will send the command to the micro:bit to turn on the LED.<P>

<span id="subtitle">Description:</span><P>

In this example, there are 2 parts involved. 

* In part 1, we need to connect the micro:bit to the internet and get the device ID. 
* In part 2, set the rule on IFTTT applet. If the time is 6 pm, set the command “light_on”

![auto_fit](images/Ch4/Ch4_2_ifttt0.png)<P>


## Part 1: Coding
<HR>

<span id="subtitle" >Goal:</span><P>
We need to get the Device ID and set the corresponding action.<BR><P>

<span id="subtitle" >Connection Diagram:</span><BR>
* Connect LED to P0<BR><P>
![auto_fit](images/Ch4/Ch4_2_hardware.png)<P>

<span id="subtitle" >Step 1: Connect WiFi</span><BR><P>
Before we try to use WiFi Control function, we need to connect to the network, we have already know how to connect to the WiFi on the first chapter.<P>
![auto_fit](images/Ch4/Ch4_2_p1.png)<P>

<span id="subtitle" >Step 2: Get Device ID</span><BR><P>
`On WiFi connected` is an event handler. It will be triggered once after connected with WiFi. The handler will provide the `Device ID` variable which used to identify and control the Microbit.

* Go to OLED Tab
* Snap `initialize OLED with width…height..` to `on start`
* Snap the `show string` inside the `On WiFi connected`
* Draw the `Device ID` variable from `On WiFi connected` to the `show string` block placeholder

![auto_fit](images/Ch4/Ch4_2_p2.png)<P>

*If you worried about forget the `Device ID` during program running, you may access it by the variable under Control tab
* Go to Control tab
* Snap the `Device ID` variable to the placeholder
![auto_fit](images/Ch4/Ch4_2_p2_1.png)<P>

<span id="subtitle" >Step 3: Control with Command</span><BR><P>

After connected to the WiFI, the connection to the server will be done automatically, it is ready to receive command though network. To get the command, we can use the `on Wi-Fi received` handler in WAN control tab.

* Snap the `on WiFi received` handler to stage
* Do the `if-condition statement` to the variable `WAN_Command`
* If `Wan_command` “light_on” is received, white LED will be turned on (intensity:1023)
* If `Wan_command` “light_off” is received, white LED will be turned off (intensity:0)

![auto_fit](images/Ch4/Ch4_2_p3.png)<P>

<span id="subtitle">Step 4: Show the Command</span><BR><P>
Sometimes you may need to show the recevied command for debugging, so if you need that, you can use the OLED `show string` to display the command on the OLED.
* Go to OLED
* Snap the `clear OLED display` to `On WiFi received` to avoid overlap
* Snap the `show string` to `On WiFi received`
* Draw the `WAN_Command` variable to `show string` placeholder

![auto_fit](images/Ch4/Ch4_2_p3_05.png)<P>

<H3><U>Advanced Usage(with value):</U></H3>

If you want to control the module with value, you can use the another block which contain `value` variable.<BR>
If `Wan command` “LightValue” is received, white LED will be turned on with the given intensity `value`.<BR>
You may also show the `WAN_Command` and `value` by `show string`.<P>
![auto_fit](images/Ch4/Ch4_2_p3_1.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_Jdb8fA66r77Y](https://makecode.microbit.org/_Jdb8fA66r77Y)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_Jdb8fA66r77Y" width="100%" height="500" frameborder="0"></iframe>

<P>

## Part 2: IFTTT Applet Configuration
<HR>

<H3>Goal:</H3>
We need to setup the IFTTT Applet to control the Mircobit


<span id="subtitle" >Step 1: Create or login to IFTTT account</span><P>
Open your browser , go to [https://ifttt.com/](https://ifttt.com/). Register your IFTTT account and once completed, log in to your IFTTT account.<BR><P>
![auto_fit](images/Ch4/Ch4_ifttt1.png)<P>


<span id="subtitle" >Step 2: Create Applets</span><BR><P>
On the top right menu, click “Create” > “Applets”<BR><P>
![auto_fit](images/Ch4/Ch4_ifttt2.png)<P>

<span id="subtitle" >Step 3: Set the Rules</span><BR><P>
On IFTTT configuration, set the below. We can set the rule on the IFTTT, if something happened like time at 6:00 p.m., we can do the corresponding action.<P>

![auto_fit](images/Ch4/Ch4_2_ifttt1.png)<P>

<span id="subtitle" ><u>A. Trigger Part</u></span><P>
![auto_fit](images/Ch4/Ch4_2_ifttt1_1.png)<P>
1.Search "Date" and select "Date & Time"<P>
![auto_fit](images/Ch4/Ch4_2_ifttt1_2.png)<P>
2.Finish the time setting.<P>
* Choose trigger "Every day at"
* Select the time (e.g. 06PM, 00Minutes; it menas every day at 6pm) and click "Create trigger"

![auto_fit](images/Ch4/Ch4_2_ifttt1_3.png)<P>

<span id="subtitle" ><u>B. Action Part</u></span><P>

![auto_fit](images/Ch4/Ch4_2_ifttt1_4.png)<P>
1.Search “micro:bit” and you will see “Smarthon IoT(micro:bit)”<P>
![auto_fit](images/Ch4/Ch4_2_ifttt1_6.png)<P>

2.Finish the mirco:bit setting.
* Choose action "Control Command"
* Input your `Device ID` (e.g. 0xa3240ac45916) and `control command` (e.g. light_on). Then click "Create action"
![auto_fit](images/Ch4/Ch4_2_ifttt1_7.png)<P>


<span id="subtitle" ><u>Optional</u></span><P>
If you need to send the command with value to the micro:bit<BR>

![auto_fit](images/Ch4/Ch4_2_ifttt1_8.png)<P>


## Result
<HR>

<H3><U>Normal Case:</U></H3>

After connected to WiFi, micro:bit will connect to control server and keep listening to the WAN command

* Every day at 6pm, clock will trigger IFTTT to send out micro:bit WAN command “light_On”
* Micro:bit will recevie the command
* The LED on P0 will be turned on.
![auto_fit](images/Ch4/Ch4_2_result.png)<P>

<H3><U>Advanced Usage(with value):</U></H3>

When change the applet to contain value version, it will have an additional variable `value` included
* Every day at 6pm, clock will trigger IFTTT to send out micro:bit WAN command “LightValue” (with value “600”)
* Micro:bit will recevie the command
* The LED on P0 will be turned on (with light intensity: 600).
![auto_fit](images/Ch4/Ch4_2_result_1.png)<P>