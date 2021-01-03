# Chapter 2: Send Email by IFTTT


IFTTT is the way to connect hundreds of the apps and devices, including Twitter, Dropbox, Email, Google Assistant, etc. By the basic programming logic "if this then that", it connects IoT services through their API (application programming interface).<P> In IFTTT, you can make your own applet and link services together by "if this(trigger) then that(action)". For example, if we select webhooks (micro:bit button A) as trigger, Email (send email to your mailbox) as action. When micro:bit button A is pressed, it triggers (webhooks) and implement the action (send email) in IFTTT.<BR><P>
![auto_fit](images/Ch2/Ch2_des1.png)<P>
In this chapter, you will learn using micro:bit to activate trigger (webhooks). After that, it can implement other services (e.g. email)<BR><P>


## IFTTT Configuration
<HR>
<H3>Goal:</H3>
Create applet and get the API key<P>


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

## Coding (Makecode)
<HR>

<span id="subtitle" >Step 1</span><BR><P>
Before we do the IFTTT uploading part, we have already know how to connect to the WiFi on the first chapter. <BR><P>
![auto_fit](images/Ch2/Ch2_p3.png)<P>

<span id="subtitle" >Step 2</span><BR><P>
When need to send ITFFF request, if `WiFi connected`, send data to IFTTT.<BR>
Input the following data of the IFTTT Application to the `Send IFTTT key…` block
<BR><P>
* `IFTTT API key`: XXXXXXXXXXXXXXXX. 
* `event_name`: event name to trigger in Webhooks (eg. SendEmail)
* `value 1-3`: if user want to add the value inside the email, click the add button and input value1, value2, value3<P>

![auto_fit](images/Ch2/Ch2_p5.png)<P>


<span id="subtitle" >Step 3</span><BR><P>
If you want to show the IFTTT upload status, you can use the “on IFTTT Uploaded” handler to check the variable. You may use the OLED to display the status and error code.<BR><P>
* Go to OLED Tab
* Snap `initialize OLED with width…height..` to `on start`
* Snap the `show string` inside the `On IFTTT Uploaded`
* Draw the variable from `On IFTTT Uploaded` to the `show string` block placeholder<P>

![auto_fit](images/Ch2/Ch2_p6.png)<P>



<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_Txv1LF34edWu](https://makecode.microbit.org/#pub:_Txv1LF34edWu)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_Txv1LF34edWu" width="100%" height="500" frameborder="0"></iframe>



## Result
<HR>

After micro:bit is connected to WiFi and click button A, it will upload data to IFTTT.<BR><P>
If the upload is success, it will show `OK` with error code `0`<P>

![auto_fit](images/Ch2/Ch2_result1.png)<P>

If the upload is fail (such input wrong API key in this case), it will show `FAIL` with `error code`.<BR>
For the error 401, the user inputted the wrong API Key. For the error code -28674, there is no internet connection.<P>

![auto_fit](images/Ch2/Ch2_result1_1.png)<P>

When success, email will be sent to your mailbox by IFTTT.<BR><P>
![auto_fit](images/Ch2/Ch2_result2.png)<P>
