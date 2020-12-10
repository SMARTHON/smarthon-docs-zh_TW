# Chapter 1: Upload Data to ThingSpeak

ThingSpeak is IoT platform for user to gather real-time data; for instance, climate information, location data and other device data. In different channels in ThingSpeak, you can summarize information and visualize data online in charts and analyze useful information.<BR> ThingSpeak can integrate IoT:bit (micro:bit) and other software/ hardware platforms. Through IoT:bit, you can upload sensors data to ThingSpeak (e.g. temperature, humidity, light intensity, noise, motion, raindrop, distance and other device information).<BR><P>
![auto_fit](images/Ch1/Ch1_des.png)<P>

## Thingspeak Configuration
<HR>

<H3>Goal:</H3> we need to create the thingspeak channel and get the key

<span id="subtitle" >Step 1</span><P>
Go to [https://thingspeak.com/](https://thingspeak.com/), register an account and login to the platform<BR><P>
![auto_fit](images/Ch1/Ch1_reg1.png)<P>

<span id="subtitle" >Step 2</span><P>
Choose Channels -> My Channels -> New Channel<BR><P>
![auto_fit](images/Ch1/Ch1_reg2.png)<P>

<span id="subtitle" >Step 3</span><P>
Input Channel name, Field1 , then click “Save Channel”<BR><P>
* Channel name: smart-house
* Field 1: Temperature
![auto_fit](images/Ch1/Ch1_reg3.png)<P>

<span id="subtitle" >Step 4</span><P>
You will see a chat for data field1 <BR><P>
![auto_fit](images/Ch1/Ch1_reg4.png)<P>

<span id="subtitle" >Step 5</span><P>
Open your web browser, go to https://thingspeak.com , select your channel > “API Keys” ，copy the API key as follows:<BR><P>
![auto_fit](images/Ch1/Ch1_reg5.png)<P>

## Coding (Makecode)
<HR>

<span id="subtitle" >Step 1</span><P>
Before we do the thingspeak uploading part, we already know how to connect to the WiFi on the first chapter.<BR>
![auto_fit](images/Ch1/Ch1_p2.png)<P>

<span id="subtitle" >Step 2</span><P>
On every 15 seconds, if the WiFi is connected, it will send data to ThingSpeak.<BR>

* Use `if-statement` inside the `forever` loop to check `WiFi connected?` status
* Snap the `Send Thingspeak key.....` block inside the `if-statement`
* Fill in the `api key` from Thingspeak and the `temperature` values
* Snap `pause` to the loop to wait 15 second<P>

![auto_fit](images/Ch1/Ch1_p3.png)<P>

<span id="subtitle" >Step 3</span><P>
If you want to show the thingspeak status, you can use the on Thingspeak Uploaded handler to get the variable for status and error code. You may use the OLED to display the status and error code.<BR>

* Go to OLED Tab
* Snap `initialize OLED with width 128 height 64` to `on start`
* Snap the `show string` inside the `On Thingspeak Uploaded`
* Draw the variable from `On Thingspeak Uploaded` to the `show string` block placeholder.<BR>

![auto_fit](images/Ch1/Ch1_p4.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_9PaTppdoCETi](https://makecode.microbit.org/#pub:_9PaTppdoCETi)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_9PaTppdoCETi" width="100%" height="500" frameborder="0"></iframe>

<P>

## Result
<HR>


After Connected to Internet, the program start upload the data to Thingspeak.<P> When the Upload is finish, it will shown the status `OK` and Error Code `0`.<BR>
![auto_fit](images/Ch1/Ch1_result1.png)<P>
If the thingspeak cannot be uploaded successfully, the status will return `FAIL` with `error code`.<BR> For the error 400, the user inputted the wrong API Key. For the error code -28674, there is no internet connection. <BR>
![auto_fit](images/Ch1/Ch1_result1_1.png)<P>
The charts in your channel in ThingSpeak will be updated.
![auto_fit](images/Ch1/Ch1_result2.png)<P>

