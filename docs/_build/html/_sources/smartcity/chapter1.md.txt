# Chapter 1: Connect the micro:bit to the Wi-Fi

Connecting Wi-Fi is the very first step to access internet services, including ThingSpeak, IFTTT, email, etc. Before you start, make sure your micro:bit device is connected to the Internet.<BR><P>
![pic_600](images/Ch1_01.png)

## Open the Home Router or Mobile Phone Hotspot
<HR>
Before you start, you need to make sure there is a Wi-Fi signal (with 2.4GHz) available in your area. <BR>
You can <B>either</B> setup a home router <B>or</B> a Wi-Fi hotspot from your mobile phone.<P>

### Setup your home/office Wi-Fi
![pic_400](images/Ch1_02.png)<BR><P>

### Setup your mobile phone Hotspot
<span id="remarks">* make sure your phone has internet service.</span><BR><P>
![pic_400](images/Ch1_03.png)<BR><P>

* For android:
![pic_400](images/Ch1_03a.png)<BR><P>
* For iPhone:</span>
![pic_400](images/Ch1_03b.png)<BR><P>


## Programming (Makecode)
<HR>

<span id="subtitle" >Step 1</span><BR><P>
Before you start, you need to initialize the WiFi IoT:bit.<BR>
Choose WiFi IoT:bit -> Initialize WiFi IoT:bit and OLED<BR><P>
![pic_600](images/Ch1_04.png)<BR>
<P>

<span id="subtitle" >Step 2</span><BR><P>
After initializing, you can connect to the WiFi:<BR>
Choose WiFi IoT:bit -> Set Wi-Fi to ssid “”, pwd “”. Enter your Wi-Fi name and password<BR><P>
![pic_600](images/Ch1_05.png)
<P>

<span id="subtitle" >Step 3</span><BR><P>
“On WiFi connected” is an event handler.<BR>
It will be triggered once after connected with WiFi.<BR><P>
![pic_600](images/Ch1_06.png)
<P>

<span id="subtitle" >Step 4</span><BR><P>
Choose Basic -> show icon “heart” inside “On WiFi connected”<BR><P>
![pic_600](images/Ch1_07.png)
<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode:[https://makecode.microbit.org/_Ydr63W8HdLDU](https://makecode.microbit.org/v2/#pub:_Ydr63W8HdLDU)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/v2/#pub:_Ydr63W8HdLDU" width="100%" height="500" frameborder="0"></iframe>


## Result
<HR>

<span id="subtitle" >Step 1</span><BR><P>
Load the program to the micro:bit and connect the micro:bit to WiFi IoT:bit.<BR><P>
![pic](images/Ch1_08.png)
<P>

<span id="subtitle" >Step 2</span><BR><P>
Wi-Fi IoT:bit will start to connect to internet, when the connection is successful, the IP Address would be shown.<BR><P>
![pic](images/Ch1_09.png)
<P>

<span id="subtitle" >Step 3</span><BR><P>
An icon “heart” will be shown on LED after WiFi is connected successfully.<BR><P>
![pic_200](images/Ch1_10.png)
<P>