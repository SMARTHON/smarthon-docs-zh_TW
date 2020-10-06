# Chapter 1: Upload Data to ThingSpeak

ThingSpeak is IoT platform for user to gather real-time data; for instance, climate information, location data and other device data. In different channels in ThingSpeak, you can summarize information and visualize data online in charts and analyze useful information. ThingSpeak can integrate IoT:bit (micro:bit) and other software/ hardware platforms. Through IoT:bit, you can upload sensors data to ThingSpeak (e.g. temperature, humidity, light intensity, noise, motion, raindrop, distance and other device information).<BR><P>
![auto_fit](images/Ch1/Ch1_des.png)<P>

## Create channel in ThingSpeak and get the key
<HR>

<span id="subtitle" >Step 1</span><P>
Go to [https://thingspeak.com/](https://thingspeak.com/), register an account and login to the platform<BR><P>
![auto_fit](images/Ch1/Ch1_reg1.png)<P>

<span id="subtitle" >Step 2</span><P>
Choose Channels -> My Channels -> New Channel<BR><P>
![auto_fit](images/Ch1/Ch1_reg2.png)<P>

<span id="subtitle" >Step 3</span><P>
Input Channel name, Field1 and Field2 , then click “Save Channel”<BR><P>
* Channel name: smart-house
* Field 1: Light
* Field 2: Temperature
![auto_fit](images/Ch1/Ch1_reg3.png)<P>

<span id="subtitle" >Step 4</span><P>
You will see two chats for data (field1, field 2)<BR><P>
![auto_fit](images/Ch1/Ch1_reg4.png)<P>

<span id="subtitle" >Step 5</span><P>
Open your web browser, go to https://thingspeak.com , select your channel > “API Keys” ，copy the API key as follows:<BR><P>
![auto_fit](images/Ch1/Ch1_reg5.png)<P>

## Programming (Makecode)
<HR>

![auto_fit](images/Ch1/Ch1_p1.png)<P>

<span id="subtitle" >Step 1</span><P>
Before you start, you need to initialize IoT:bit and connect micro:bit to the internet. <BR><P>
Select `IoT:bit` > `Initialize IoT:bit and OLED` and `Set WiFi to ssid…pwd`. <BR><P>
![auto_fit](images/Ch1/Ch1_p2.png)<P>

<span id="subtitle" >Step 2</span><P>
Snap `if` statement into `forever`, set `if WiFi is connected`.<BR><P>
![auto_fit](images/Ch1/Ch1_p3.png)<P>

<span id="subtitle" >Step 3</span><P>
On every 15seconds, if the WiFi is connected, it will send data to ThingSpeak.
![auto_fit](images/Ch1/Ch1_p4.png)<P>

<span id="subtitle" >Step 4</span><P>
Open your program and paste the ThingSpeak key. You can also remove/add the input field and change the upload value.<BR><P>
![auto_fit](images/Ch1/Ch1_p5.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_gHM58bgf5e41](https://makecode.microbit.org/#pub:_gHM58bgf5e41)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_gHM58bgf5e41" width="100%" height="500" frameborder="0"></iframe>


## Result
<HR>

Micro:bit start uploading, “thingspeak uploading… “ is shown.<BR><P>
If data is uploaded successfully, “Uploaded OK” will be shown.<BR><P>
![auto_fit](images/Ch1/Ch1_result1.png)<P>
The charts in your channel in ThingSpeak will be updated.<BR><P>
![auto_fit](images/Ch1/Ch1_result2.png)<P>

