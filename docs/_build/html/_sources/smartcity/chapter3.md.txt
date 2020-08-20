# Chapter 3: Send Email by IFTTT

IFTTT is the way to connect hundreds of the apps and devices, including Twitter, Dropbox, Email, Google Assistant, etc. You can connect Micro:bit to IFTTT to create more features by “If… then…”.
![pic](images/Ch3_01.png)

## Create event “Email” in IFTTT and get the key
<span id="subtitle" >Step 1</span>
* Go to http://www.ifttt.com, open the top right menu, then click “Create” > “Applets”
![pic](images/Ch3_02.png)

<span id="subtitle" >Step 2</span>
* Select this -> select webhooks -> input Event Name (eg. Event Name: SendEmail)，then click “Create trigger” 
![pic](images/Ch3_03.png)

<span id="subtitle" >Step 3</span>
* Select “That” > Email
![pic](images/Ch3_04.png)

<span id="subtitle" >Step 4</span>
* Select “Send me an email” , Input email title and body, then click “Create action” 
![pic](images/Ch3_05.png)

<span id="subtitle" >Step 5</span>
* Open your web browser, open the top right menu, select “My services” > “Webhooks” 
![pic](images/Ch3_06.png)

<span id="subtitle" >Step 6</span>
* Select “Documentation” ，Copy your Webhooks Key as follows:
![pic](images/Ch3_07.png)

## Programming (Makecode)

<span id="subtitle" >Step 1</span>
* It will trigger the following function once after button A is clicked
![pic_200](images/Ch3_08.png)

<span id="subtitle" >Step 2</span>
* This function will send data (field1, field2, field3) and trigger event to IFTTT with the key provided
![pic_200](images/Ch3_09.png)

<span id="subtitle" >Step 3</span>
* Select “WiFi IoT:bit” > “Initialize WiFi Iot:bit and OLED” and “Set WiFi to ssid…pwd”. 
* Select “Input” ->“on button A pressed” .
![pic](images/Ch3_10.png)

<span id="subtitle" >Step 4</span>
* Select “WiFi IoT:bit” > “Send IFTTT key….” 
* Once button A is clicked, it will send IFTTT request (send an email to your email box) 
![pic](images/Ch3_11.png)

<span id="subtitle" >Step 5</span>
* Input the following value
a. IFTTT API key: “HnXXXXXXXXXXXXXjb “. 
b. event_name: event name to trigger in Webhooks (eg. SendEmail)
c. value 1-3: input value1, value2, value3
![pic](images/Ch3_12.png)

## Result
* After micro:bit is connected to WiFi and click button A, it will upload data to IFTTT.
* If data is uploaded successfully, “Uploaded OK” will be shown. 
![pic](images/Ch3_13.png)

* Email will be sent to your mailbox by IFTTT.
![pic](images/Ch3_14.png)

