# Chapter 1: Upload Data to ThingSpeak

ThingSpeak is a great platform for user to uploading data for IOT. It allows you to create channel for uploading data. You can visualize the information in charts, for data visualization.
![auto_fit](images/Ch2_01.png)
 

## Create channel in ThingSpeak
<span id="subtitle" >Step 1</span>
* Go to https://thingspeak.com/, register an account and login to the platform

<span id="subtitle" >Step 2</span>
* Choose Channels -> My Channels -> New Channel
![pic_60](images/Ch2_02.png)

<span id="subtitle" >Step 3</span>
* Input Channel name, Field1 and Field2 , then click “Save Channel”
> * Channel name: smart-house
> * Field 1: Light
> * Field 2: Temperature
> ![pic_60](images/Ch2_03.png)

<span id="subtitle" >Step 4</span>
* You will see two chats for data (field1, field 2)
![auto_fit](images/Ch2_04.png)

<span id="subtitle" >Step 5</span>
* Open your web browser, go to https://thingspeak.com , select your channel > “API Keys” ，copy the API key as follows:
![auto_fit](images/Ch2_05.png)


## Programming (Makecode)
<span id="subtitle" >Step 1</span>
* if WiFi is connected, it returns true, otherwise it returns false.
![pic_50](images/Ch2_06.png)

<span id="subtitle" >Step 2</span>
* It will send data (field1, field2, field3) to Thingspeak with the key provided
![pic_50](images/Ch2_07.png)

<span id="subtitle" >Step 3</span>
* Select “WiFi IoT:bit” > “Initialize WiFi Iot:bit and OLED” and “Set WiFi to ssid…pwd”. 
* On every 15seconds, if the WiFi is connected, it will send data to ThingSpeak.
![auto_fit](images/Ch2_08.png)

<span id="subtitle" >Step 4</span>
* Open your program and paste the ThingSpeak key and paste it here.
![auto_fit](images/Ch2_09.png)

## Result
* If data is uploaded successfully, “Uploaded OK” will be shown.
![auto_fit](images/Ch2_10.png)
* The charts in your channel in ThingSpeak will be updated.
![auto_fit](images/Ch2_11.png)
