# First step: Connect the micro:bit to the Wi-Fi

Connecting Wi-Fi is the very first step to access internet services, including ThingSpeak, IFTTT, email, etc. Before you start, make sure your micro:bit device is connected to the Internet.<BR><P>
![auto_fit](images/4_ConnectWiFi/Wifi_01.png)<P>


## Open the Home Router or Mobile Phone Hotspot
<HR>

Please sure there is a Wi-Fi signal (with 2.4GHz) available in your area. <BR>
*5GHz Wi-Fi signal is not supported<P>
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
Before you start, you need to initialize the IoT:bit.<BR>
* Go to IoT:bit tab.
* Snap `Initialize IoT:bit TX P16 RX P8` to `on start`
![auto_fit](images/4_ConnectWiFi/Wifi_p1.png)<P>

<span id="subtitle">Step 2: Connect to the Wi-Fi</span><BR><P>
After initializing, you can connect to the Wi-Fi<BR>
* Go to IoT:bit tab
* Snap `Set Wi-Fi to ssid pwd` to `on start` following initialize
* Enter your Wi-Fi name and password. Here we set `smarthon` as `SSID` and “12345678” as `password`.
![auto_fit](images/4_ConnectWiFi/Wifi_p2.png)<P>

<span id="subtitle">Step 3: Show the Tick if it is connected</span><BR><P>
`On WiFi connected` is an event handler. It will be triggered once after connected with WiFi.
After the WiFi is connected, it provide two variable `IP_Address` and `Device_ID` for you to 
control the IoT:bit though network.<BR>
* Snap `On WiFi connected` to the stage
* On `Basic` tab, snap `show icon heart` inside `On WiFi connected`
* Swtich the heart to tick<BR>

![auto_fit](images/4_ConnectWiFi/Wifi_p3.png)<P>

<span id="subtitle">Step 4: Show you IP</span><BR><P>
If you want to see the IP address, you may show it on the OLED display.<BR>
* Go to OLED tab
* Snap “initialize OLED with width…height..” to on start 
* Snap the “show string“ inside the On WiFi connected 
* Draw the variable from On WiFi connected to the “show string” block placeholder
* You may control the text format by the function in Text tab<BR>

![auto_fit](images/4_ConnectWiFi/Wifi_p3_5.png)<P>

<B><u>Optional</u></B>:<BR>
On WiFi disconnected handler will be triggered when the WiFi connection is loss, it may useful when you get disconnection to the WiFi Station during the application running.<BR>

![auto_fit](images/4_ConnectWiFi/Wifi_p5.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_53Yf8qcx521m](https://makecode.microbit.org/_53Yf8qcx521m)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_53Yf8qcx521m" width="100%" height="500" frameborder="0"></iframe>


## Result
<HR>

<span id="subtitle">Step 1</span><BR><P>
Load the program to the micro:bit and turn on the IoT:bit by using USB<BR><P>.
![auto_fit](images/4_ConnectWiFi/Wifi_result1.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Wi-Fi IoT:bit will start to connect to internet, when the connection is successful, the IP Address would be shown. AND the tick icon will be shown.<BR><P>
![auto_fit](images/4_ConnectWiFi/Wifi_result2.png)<P>

After the IoT:bit is connected to the wifi, when disconnect to the router. It will show “cross” symbol and the error code will be shown. Normally, the code `201` means “No AP Found”. <BR>The reason might be:
1. Router is too far away
2. No that AP actually 
3. The typo on SSID/PWD

![auto_fit](images/4_ConnectWiFi/Wifi_result3.png)<P>
