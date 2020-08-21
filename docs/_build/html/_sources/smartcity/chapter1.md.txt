# Chapter 1: Connect the micro:bit to the Wi-Fi

Connecting WiFi is the very first step to access internet services, including ThingSpeak, IFTTT, email, etc. Before you start, make sure your micro:bit device is connected to the Internet.
![pic_600](images/Ch1_01.png)

## Open Home Wi-Fi/Office Wi-Fi/Mobile phone Hotspot (Router)
Before you start, you need to make sure there are wireless internet service (with 2.4GHz) available in your area. You can either access your home/office WiFi or set a WiFi hotspot in your mobile phone.

### Access your home/office WiFi
![pic_400](images/Ch1_02.png)

 
### Set your mobile Hotspot
* make sure your phone is connected to the internet first
![pic_400](images/Ch1_03.png)


## Programming (Makecode)
<span id="subtitle" >Step 1</span>
* Before you start, you need to initialize the WiFi IoT:bit.
* Choose WiFi IoT:bit -> Initialize WiFi IoT:bit and OLED
![pic_600](images/Ch1_04.png)

<span id="subtitle" >Step 2</span>
* After initializing, you can connect to the WiFi:
* Choose WiFi IoT:bit -> Set Wi-Fi to ssid “”, pwd “”. Enter your Wi-Fi name and password
![pic_600](images/Ch1_05.png)

<span id="subtitle" >Step 3</span>
* “On WiFi connected” is an event handler.
* It will be triggered once after connected with WiFi.
![pic_600](images/Ch1_06.png)

<span id="subtitle" >Step 4</span>
* Choose Basic -> show icon “heart” inside “On WiFi connected”
![pic_600](images/Ch1_07.png)


## Result
<span id="subtitle" >Step 1</span>
* Load the program to the micro:bit and connect the micro:bit to WiFi IoT:bit.
![pic](images/Ch1_08.png)

<span id="subtitle" >Step 2</span>
* Wi-Fi IoT:bit will start to connect to internet, when the connection is successful, the IP Address would be shown. 
![pic_600](images/Ch1_09.png)

<span id="subtitle" >Step 3</span>
* An icon “heart” will be shown on LED after WiFi is connected successfully.
![pic](images/Ch1_10.png)
