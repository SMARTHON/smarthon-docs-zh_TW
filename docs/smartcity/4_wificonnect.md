# First step: Connect the micro:bit to the Wi-Fi

Connecting Wi-Fi is the very first step to access internet services, including ThingSpeak, IFTTT, email, etc. Before you start, make sure your micro:bit device is connected to the Internet.<BR><P>
![auto_fit](images/4_ConnectWiFi/Wifi_01.png)<P>


## Open the Home Router or Mobile Phone Hotspot
<HR>

Please sure there is a Wi-Fi signal (with 2.4GHz) available in your area. <BR><P>
You can either setup a home router or a Wi-Fi hotspot from your mobile phone.<BR><P>

<span id="subtitle">a) Setup your home/office Wi-Fi</span><BR><P>
![auto_fit](images/4_ConnectWiFi/Wifi_02.png)<P>

<span id="subtitle">b) Setup your mobile phone Hotspot </span><BR><P>
<span id="remarks">* make sure your phone has internet service.</span><BR><P>
![auto_fit](images/4_ConnectWiFi/Wifi_03.png)<P>

<span id="subtitle">For android:</span><BR><P>
![auto_fit](images/4_ConnectWiFi/Wifi_03a.png)<P>
<span id="subtitle">For iPhone:</span><BR><P>
![auto_fit](images/4_ConnectWiFi/Wifi_03b.png)<P>


## Programming (Makecode)
<HR>

<span id="subtitle">Step 1: Initialize the IoT:bit</span><BR><P>
Before you start, you need to initialize the IoT:bit, go to IoT:bit tab.<BR><P>
* Snap “Initialize IoT:bit at OLED height: 64, width:128 Wifi info shown: true” to “on start”
![auto_fit](images/4_ConnectWiFi/Wifi_p1.png)<P>

<span id="subtitle">Step 2: Connect to the Wi-Fi</span><BR><P>
After initializing, you can connect to the Wi-Fi<BR><P>
* Snap “Set Wi-Fi to ssid pwd” to “on start”
* Enter your Wi-Fi name and password. Here we set “wifi_name” as SSID and “12345678” as password.
![auto_fit](images/4_ConnectWiFi/Wifi_p2.png)<P>

<span id="subtitle">Step 3: Show the Heart if it is connected</span><BR><P>
On WiFi connected” is an event handler. It will be triggered once after connected with WiFi.<BR><P>
* Snap “On WiFi connected” to the stage
* On “Basic” tab, snap “show icon heart inside “On WiFi connected”
![auto_fit](images/4_ConnectWiFi/Wifi_p3.png)<P>
![auto_fit](images/4_ConnectWiFi/Wifi_p4.png)<P>

## Result
<HR>

<span id="subtitle">Step 1</span><BR><P>
Load the program to the micro:bit and turn on the IoT:bit by using USB<BR><P>.
![auto_fit](images/4_ConnectWiFi/Wifi_result1.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Wi-Fi IoT:bit will start to connect to internet, when the connection is successful, the IP Address would be shown. AND the heart icon will be shown.<BR><P>
![auto_fit](images/4_ConnectWiFi/Wifi_result2.png)<P>
