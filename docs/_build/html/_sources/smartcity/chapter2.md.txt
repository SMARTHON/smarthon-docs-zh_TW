# Chapter 2: Send Email by IFTTT


IFTTT is the way to connect hundreds of the apps and devices, including Twitter, Dropbox, Email, Google Assistant, etc. By the basic programming logic "if this then that", it connects IoT services through their API (application programming interface). In IFTTT, you can make your own applet and link services together by "if this(trigger) then that(action)". For example, if we select webhooks (micro:bit button A) as trigger, Email (send email to your mailbox) as action. When micro:bit button A is pressed, it triggers (webhooks) and implement the action (send email) in IFTTT.<BR><P>
![auto_fit](images/Ch2/Ch2_des1.png)<P>
In this chapter, you will learn using micro:bit to activate trigger (webhooks). After that, it can implement other services (e.g. email)<BR><P>


## Create event “Email” in IFTTT and get the key
<HR>

<span id="subtitle" >Step 1</span><BR><P>
Go to [http://www.ifttt.com](http://www.ifttt.com), register an account and login to the platform<BR><P>
![auto_fit](images/Ch2/Ch2_ifttt1.png)<P>
<span id="subtitle" >Step 2</span><BR><P>
On the top right menu, click “Create” > “Applets”<BR><P>
![auto_fit](images/Ch2/Ch2_ifttt2.png)<P>
<span id="subtitle" >Step 3</span><BR><P>
Select this -> select webhooks -> input Event Name (eg. Event Name: SendEmail)，then click “Create trigger” <BR><P>
![auto_fit](images/Ch2/Ch2_ifttt3.png)<P>
<span id="subtitle" >Step 4</span><BR><P>
Select “That” > Email<BR><P>
![auto_fit](images/Ch2/Ch2_ifttt4.png)<P>
<span id="subtitle" >Step 5</span><BR><P>
Select “Send me an email” , Input email title and body, then click “Create action” <BR><P>
![auto_fit](images/Ch2/Ch2_ifttt5.png)<P>
<span id="subtitle" >Step 6</span><BR><P>
Open your web browser, open the top right menu, select “My services” > “Webhooks” <BR><P>
![auto_fit](images/Ch2/Ch2_ifttt6.png)<P>
<span id="subtitle" >Step 7</span><BR><P>
Select “Documentation” ，Copy your Webhooks Key as follows:<BR><P>
![auto_fit](images/Ch2/Ch2_ifttt7.png)<P>

## Programming (Makecode)
<HR>

<span id="subtitle" >On button A pressed:</span><BR><P>
![auto_fit](images/Ch2/Ch2_p1.png)<P>
It will trigger the following function once after button A is clicked<BR><P>

<span id="subtitle" >Send IFTTT key “”, event name “” value1””:</span><BR><P>
![auto_fit](images/Ch2/Ch2_p2.png)<P>
This function will trigger webhooks to IFTTT with the key provided<BR><P>
a. Event name: webhooks event name<BR><P>
b. Value1,2,3: you can send values to IFTTT<BR><P>


<span id="subtitle" >Step 1</span><BR><P>
Before you start, you need to initialize IoT:bit and connect micro:bit to the internet. <BR><P>
Select “IoT:bit” > “Initialize IoT:bit and OLED” and “Set WiFi to ssid…pwd”.<BR><P> 
![auto_fit](images/Ch2/Ch2_p3.png)<P>

<span id="subtitle" >Step 2</span><BR><P>
Select “Input” ->“on button A pressed” .<BR><P>
![auto_fit](images/Ch2/Ch2_p4.png)<P>

<span id="subtitle" >Step 3</span><BR><P>
Select “IoT:bit” > “Send IFTTT key….” <BR><P>
Once button A is clicked, it will send IFTTT request (send an email to your email box) <BR><P>
![auto_fit](images/Ch2/Ch2_p5.png)<P>

<span id="subtitle" >Step 4</span><BR><P>
Input the following value<BR><P>
a. IFTTT API key: “XXXXXXXXXXXXXXXXX “. <BR><P>
b. event_name: event name to trigger in Webhooks (eg. SendEmail)<BR><P>
c. value 1-3: input value1, value2, value3<BR><P>
![auto_fit](images/Ch2/Ch2_p6.png)<P>

## Result
<HR>

After micro:bit is connected to WiFi and click button A, it will upload data to IFTTT.<BR><P>
Micro:bit start uploading, “ifttt uploading… “ is shown. <BR><P>
If data is uploaded successfully, “Uploaded OK” will be shown. <BR><P>
![auto_fit](images/Ch2/Ch2_result1.png)<P>

Email will be sent to your mailbox by IFTTT.<BR><P>
![auto_fit](images/Ch2/Ch2_result2.png)<P>
