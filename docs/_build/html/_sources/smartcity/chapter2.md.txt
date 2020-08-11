# Chapter 2: [Data visualization] Upload Data to ThingSpeak

## Create channel in ThingSpeak

This is a channel for uploading data. You can visualize the information in charts, for data visualization.
![pic](images/Ch2_01.png)

1. Go to https://thingspeak.com/, Register and account and login to the platform

2. Choose Channels -> My Channels -> New Channel
![pic](images/Ch2_02.png)

3. Input Channel name (3A-G1-smart-house), Field1(light) and Field2(temperature), then click “Save Channel”
![pic](images/Ch2_03.png)

4. You will see two charts for data (field1, field 2)
![pic](images/Ch2_04.png)

5. Open your web browser, go to https://thingspeak.com , select your channel >「API Keys」，copy the API key as follows:
![pic](images/Ch2_05.png)

## Connect with ThingSpeak by Micro:bit (makecode)

1. if WiFi is connected, it returns true, otherwise it returns false.
![pic](images/Ch2_06.png)

2. It will send data (field1, field2, field3) to Thingspeak with the key provided
![pic](images/Ch2_07.png)

3. On every 15seconds, if the WiFi is connected, it will send data to ThingSpeak.
![pic](images/Ch2_08.png)


4. Open your program and paste the ThingSpeak key and paste it here.
![pic](images/Ch2_09.png)

## Test it!

If data is uploaded successfully, “Uploaded OK” will be shown.
![pic](images/Ch2_10.png)

