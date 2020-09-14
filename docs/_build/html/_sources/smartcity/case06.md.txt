# IoT Case 06: Weather Station 

Level: ![level](images/level2.png)

## Goal
<HR>
Make a weather station which gets the values from the raindrop sensor, temperature and humidity sensor. The data will be sent to IoT platform - ThingSpeak.<BR><P>

## Background
<HR>

<span id="subtitle">What is Thingspeak?</span><P>
ThingSpeak is an IoT analytics platform service which provides instant visualizations of data posted by your devices to ThingSpeak. In this case, we will use this platform to update our data to plot instant graphs. <BR><P>

<span id="subtitle">Weather station operation</span><P>
Collecting temperature, humidity and raindrop consistently and uploading the data by using Thingspeak. This can help us to do analytical work more conveniently as we can refer to the automatically plotted graphs. <BR><P>

## Part List
<HR>
<table><tr><td>
Electronics:
<ul display='inline-block'>
<li>micro:bit X1</li>
<li>Smarthon IoT:bit X1</li>
<li>OLED X1</li>
<li>USB Wire/Battery Holder </li>
&nbsp;&nbsp;1.	Temperature and humidity Sensor (With Module wire)<BR>
&nbsp;&nbsp;2.	Raindrop Sensor (With Module wire)<BR>
</ul>
</td></tr>

<tr>
<td>Model:
<ul>
<li>House Model H1-H2 X1</li>
<li>M4 Screw X4</li>
<li>M4 Nuts X4</li>
</ul>
</td></tr>
<tr><td>Equipment:
<ul><li>ScrewDriver X1</li></ul></td></tr></table>

![auto_fit](images/Case6/Case6_001.png)<P>

## Practical operation
<HR>

<span id="subtitle">Step 1</span><BR><P>
Attach the raindrop sensor to H2 model.<BR><P>
![auto_fit](images/Case6/Case6_002.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Attach the temperature and humidity sensor to H2 model.<BR><P>
![auto_fit](images/Case6/Case6_003.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Put together all the cardboard parts (H1-H2).<BR><P>
![auto_fit](images/Case6/Case6_004.png)<P>

## Hardware connect
<HR>

Connect the Raindrop Sensor to P0 port of Smarthon IoT:bit<BR><P>
Connect the Temperature and humidity Sensor to P2 port of Smarthon IoT:bit<BR><P>
![auto_fit](images/Case6/Case6_005.png)<P>

## IoT (ThingSpeak)

<span id="remarks">* For more details, please refer to Ch1.1. Create channel in ThingSpeak and get the key</span><BR><P>

<HR>

<span id="subtitle">Step 1</span><BR><P>
Go to [https://thingspeak.com/](https://thingspeak.com/), Choose Channels -> My Channels -> New Channel<BR><P>
![auto_fit](images/Case6/Case6_006.png)<P>
  
<span id="subtitle">Step 2</span><BR><P>
Input Channel name, Field1 and Field2 , then click “Save Channel”<BR><P>
* Channel name: Smart Weather Station
* Field 1: temperature
* Field 2: humidity
* Freld 3: raindrop

<span id="subtitle">Step 3</span><BR><P>
Select your channel > “API Keys” ，copy the API key as follows:<BR><P>
![auto_fit](images/Case6/Case6_007.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1</span><BR><P>
Drag on start block from Basic. Drag Initialize WiFi IoT:bit and OLED from WiFi IoT:bit and set WiFi to ssid “wifi_name” and pwd “WiFi_password”.<BR><P>
![auto_fit](images/Case6/Case6_008.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Set variable temperature, humidity and raindrop to 0.<BR><P>
![auto_fit](images/Case6/Case6_009.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Drag forever block from Basic. Snap if statement into forever. If WiFi is connected then, set humidity and temperature to get humidity and temperature values from DHT11 at Pin P2. Also, set raindrop to get raindrop value (percentage) from raindrop sensor at Pin P0.<BR><P>
![auto_fit](images/Case6/Case6_010.png)<P>
<span id="subtitle">Step 4</span><BR><P>
Show string Temperature, humidity and raindrop on the OLED by using join from text.<BR><P>
![auto_fit](images/Case6/Case6_011.png)<P>
<span id="subtitle">Step 5</span><BR><P>
Drag Send Thingspeak with key (paste thingspeak key) from WiFi IoT:bit. Set field 1 to temperature, set field 2 to humidity and set field 3 to raindrop.<BR><P>
![auto_fit](images/Case6/Case6_012.png)<P>
<span id="subtitle">Step 6</span><BR><P>
Pause for 11000ms after sending data to Thingspeak.<BR><P>
![auto_fit](images/Case6/Case6_013.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_LAkCCuesED5f](https://makecode.microbit.org/v2/#pub:_LAkCCuesED5f)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/v2/#pub:_LAkCCuesED5f" width="100%" height="500" frameborder="0"></iframe>

## Result
<HR>

When micro:bit is connected to WiFi, it will check weather information (temperature, humidity from Temperature and humidity Sensor and raindrop from raindrop sensor). Then, those data will be sent to ThingSpeak and pause for 11 seconds for another update.<BR><P>
![auto_fit](images/Case6/Case6_014.png)<P>
We can find three graphs on Thingspeak including temperature, humidity and raindrop (field1, field2, field3) respectively by collecting data using different sensors.<BR><P>
![auto_fit](images/Case6/Case6_015.png)<P>

## Think
<HR>

Q1. How can we upload other module values (e.g. noise) to ThingSpeak?<BR><P>

