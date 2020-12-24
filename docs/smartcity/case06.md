# IoT Case 06: Weather Station 

Level: ![level](images/level2.png)
![auto_fit](images/Case6/case-06.png)<P>

## Goal
<HR>

Make a weather station which gets the values from the raindrop sensor, temperature and humidity sensor. The data will be sent to IoT platform - ThingSpeak.<BR><P>

## Background
<HR>

<span id="subtitle">What is Thingspeak?</span><BR><P>
ThingSpeak is an IoT analytics platform service which provides instant visualizations of data posted by your devices to ThingSpeak. In this case, we will use this platform to update our data to plot instant graphs. <BR><P>

<span id="subtitle">Weather station operation</span><BR><P>
Collecting temperature, humidity and raindrop consistently and uploading the data by using Thingspeak. This can help us to do analytical work more conveniently as we can refer to the automatically plotted graphs.<BR><P>
![pic_70](images/Case6/Concept-diagram-Case6.png)<P>

## Part List
<HR>

![auto_fit](images/Case6/Case6_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle"> Step 1</span><BR><P>
Attach the raindrop sensor to F2 model.<BR><P>
![auto_fit](images/Case6/Case6_ass1.png)<P>
<span id="subtitle"> Step 2</span><BR><P>
Attach the temperature and humidity sensor to F2 model.
![auto_fit](images/Case6/Case6_ass2.png)<P>
<span id="subtitle"> Step 3</span><BR><P>
Put together all the cardboard parts (F1-F2).
![auto_fit](images/Case6/Case6_ass3.png)<P>
<span id="subtitle"> Step 4</span><BR><P>
Assembly completed!
![pic_60](images/Case6/Case6_ass4.png)<P>

## Hardware connect
<HR>

Connect the Raindrop Sensor to P0 port of IoT:bit<BR><P>
Connect the Temperature and humidity Sensor to P2 port of IoT:bit<BR><P>
![auto_fit](images/Case6/Case6_hardware.png)<P>


## IoT (ThingSpeak)
<HR>

<span id="remarks">* For more details, please refer to Chapter 1: Upload Data to ThingSpeak</span><BR><P>

<span id="subtitle"> Step 1</span><BR><P>
Go to [https://thingspeak.com](https://thingspeak.com/), Choose Channels -> My Channels -> New Channel<BR><P>
![auto_fit](images/Case6/Case6_iot1.png)<P>
  
<span id="subtitle"> Step 2</span><BR><P>
Input Channel name, Field1 and Field2 , then click “Save Channel”<BR><P>
* Channel name: Smart Weather Station
* Field 1: temperature
* Field 2: humidity
* Freld 3: raindrop


<span id="subtitle"> Step 3</span><BR><P>
Select your channel > “API Keys” ，copy the API key as follows:<BR><P>
![auto_fit](images/Case6/Case6_iot2.png)<P>


## Programming (MakeCode)
<HR>

<span id="subtitle"> Step 1</span><BR><P>
Initialize OLED and IoT:bit and connect to WiFi. <BR><P>
* Snap `Initialize OLED with width:128, height: 64` to `on start`
* Snap `Initialize IoT:bit TX P16 RX P8` from `IoT:bit` to `on start`
* Snap `Set Wi-Fi to ssid pwd` from `IoT:bit`
* Enter your Wi-Fi name and password. Here we set `smarthon` as `SSID` and `12345678` as `password`
* Set variable `raindrop`, `humidity` and `temperature` to 0 from `variables`
![auto_fit](images/Case6/Case6_p1.png)<P>

<span id="subtitle"> Step 2</span><BR><P>
Show icon "tick" after WiFi connection. <BR><P>
* Snap `show icon` from `basic` to `On WiFi connected` and select icon `tick`
![auto_fit](images/Case6/Case6_p2.png)<P>

<span id="subtitle"> Step 3</span><BR><P>
Get values from Temperature and Humidity sensor (DHT11) and raindrop sensor. <BR><P>
* Snap `if statement` to block `forever`
* If `WiFi is connected`
* Then, set `humidity` to `read humidity from DHT11 at Pin P2`
* Set `temperature` to `read temperature from DHT11` 
* Set `raindrop` to `get raindrop value (percentage) at Pin P0`
![auto_fit](images/Case6/Case6_p3.png)<P>

<span id="subtitle"> Step 4</span><BR><P>
Show string Temperature, humidity and raindrop on the OLED by using join from text. <BR><P>
* Snap `clear OLED display` from `OLED` to avoid overlap
* Snap `show string` and show value of variables `Temperature`, `Humidity` and `Raindrop`
![auto_fit](images/Case6/Case6_p4.png)<P>

<span id="subtitle"> Step 5. Upload data to ThingSpeak</span><BR><P>
* Snap `Send Thingspeak key...` inside the `if-statement`
* Fill in the `api key` from Thingspeak with temperature, humidity and raindrop value
* Snap `pause` to the loop to wait 15 second
![auto_fit](images/Case6/Case6_p5.png)<P>

<span id="subtitle"> Step 6. Show ThingSpeak upload status</span><BR><P>
* Snap `show string` inside `On Thingspeak Uploaded`
* Draw the variable `Status` and `Error_code` to block `show string`
![auto_fit](images/Case6/Case6_p6.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_F9q1r4comWfR](https://makecode.microbit.org/#pub:_F9q1r4comWfR)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_F9q1r4comWfR" width="100%" height="500" frameborder="0"></iframe>


## Result
<HR>

When micro:bit is connected to WiFi, it will check weather information (temperature, humidity from Temperature and humidity Sensor and raindrop value from raindrop sensor). Then, those data will be sent to ThingSpeak and pause for 15 seconds for another update.<BR><P>
![auto_fit](images/Case6/Case6_result1.png)<P>
We can find three graphs on Thingspeak including temperature, humidity and raindrop (field1, field2, field3) respectively by collecting data using different sensors.<BR><P>
![auto_fit](images/Case6/Case6_result2.png)<P>

## Think
<HR>

Q1. How can we upload other module values (e.g. noise) to ThingSpeak?<BR><P>
