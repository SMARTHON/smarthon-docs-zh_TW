# IoT Case 06: Weather Station 

Level: ![level](images/level2.png)

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

<table><tr><td>
Electronics:
<ul display='inline-block'>
<li>micro:bit X1</li>
<li>IoT:bit(with OLED) X1</li>
<li>3-pin-module wire X2 </li>
&nbsp;&nbsp;1. Temperature and humidity Sensor X1 <BR>
&nbsp;&nbsp;2. Raindrop Sensor X1 <BR>
</ul>
</td></tr>
<tr>
<td>Model:
<ul>
<li>House Model F1-F2 X1</li>
<li>M4 Screws X4</li>
<li>M4 Nuts X4</li>
</ul>
</td></tr>
<tr><td>Equipment:
<ul><li>ScrewDriver X1</li></ul></td></tr></table>

![auto_fit](images/Case6/Case6_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle"> Step 1</span><BR><P>
Attach the raindrop sensor to F2 model.<BR><P>
![auto_fit](images/Case6/Case6_po1.png)<P>

<span id="subtitle"> Step 2</span><BR><P>
Attach the temperature and humidity sensor to F2 model.<BR><P>
![auto_fit](images/Case6/Case6_po2.png)<P>

<span id="subtitle"> Step 3</span><BR><P>
Put together all the cardboard parts (F1-F2).<BR><P>
![auto_fit](images/Case6/Case6_po3.png)<P>


## Hardware connect
<HR>

Connect the Raindrop Sensor to P0 port of IoT:bit<BR><P>
Connect the Temperature and humidity Sensor to P2 port of IoT:bit<BR><P>
![auto_fit](images/Case6/Case6_hardware.png)<P>


## IoT (ThingSpeak)
<HR>

* For more details, please refer to Chapter 1: Upload Data to ThingSpeak
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
Drag on start block from Basic. Drag Initialize IoT:bit at OLED from IoT:bit, set OLED height:64, width:128. Set WiFi to ssid “wifi_name” and pwd “WiFi_password”.<BR><P>
![auto_fit](images/Case6/Case6_p1.png)<P>
<span id="subtitle"> Step 2</span><BR><P>
Set variable temperature, humidity and raindrop to 0.
![auto_fit](images/Case6/Case6_p2.png)<P>
<span id="subtitle"> Step 3</span><BR><P>
Drag forever block from Basic. Snap if statement into forever. If WiFi is connected then, set humidity and temperature to get humidity and temperature values from DHT11 at Pin P2. Also, set raindrop to get raindrop value (percentage) from raindrop sensor at Pin P0.<BR><P>
![auto_fit](images/Case6/Case6_p3.png)<P>
<span id="subtitle"> Step 4</span><BR><P>
Show string Temperature, humidity and raindrop on the OLED by using join from text.<BR><P>
![auto_fit](images/Case6/Case6_p4.png)<P>
<span id="subtitle"> Step 5</span><BR><P>
Drag Send Thingspeak with key (paste thingspeak key) from IoT:bit.. Set field 1 to temperature, set field 2 to humidity and set field 3 to raindrop.<BR><P>
![auto_fit](images/Case6/Case6_p5.png)<P>
<span id="subtitle"> Step 6</span><BR><P>
Pause for 11000ms after sending data to Thingspeak.<BR><P>
![auto_fit](images/Case6/Case6_p6.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_h8MdVLFWWcf8](https://makecode.microbit.org/#pub:_h8MdVLFWWcf8)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_h8MdVLFWWcf8" width="100%" height="500" frameborder="0"></iframe>


## Result
<HR>

When micro:bit is connected to WiFi, it will check weather information (temperature, humidity from Temperature and humidity Sensor and raindrop value from raindrop sensor). Then, those data will be sent to ThingSpeak and pause for 11 seconds for another update.<BR><P>
![auto_fit](images/Case6/Case6_result1.png)<P>
We can find three graphs on Thingspeak including temperature, humidity and raindrop (field1, field2, field3) respectively by collecting data using different sensors.<BR><P>
![auto_fit](images/Case6/Case6_result2.png)<P>

## Think
<HR>

Q1. How can we upload other module values (e.g. noise) to ThingSpeak?<BR><P>
