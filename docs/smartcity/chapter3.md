# Chapter 3: Send Email by IFTTT

## Create event “Email” in IFTTT

1. Go to http://www.ifttt.com, open the top right menu, then click「Create」
![pic](images/Ch3_01.png)

2. Select this -> select webhooks -> input Event Name (eg. Event Name: SendEmail)，then click "Create trigger"
![pic](images/Ch3_02.png)
![pic](images/Ch3_03.png)

3. Select "That" > Email
![pic](images/Ch3_04.png)

4. Select "Send me an email", Input email title and body, then click "Create action"
![pic](images/Ch3_05.png)


## Find your IFTTT key

1. Open your web browser, open the top right menu, select「My services」>「Webhooks」。
![pic](images/Ch3_06.png)

2. Select「Documentation」，Copy your Webhooks Key as follows:
![pic](images/Ch3_07.png)


## Trigger Email by IFTTT in MakeCode

1. It will trigger the following function once after connected with WiFi.
![pic](images/Ch3_08.png)

2. This function will send data (field1, field2, field3) and trigger event to IFTTT with the key provided
![pic](images/Ch3_09.png)

3. Select「IoT」> 「On WiFi connected」 and 「IoT」>「Send IFTTT key….」.
![pic](images/Ch3_10.png)

4. Once WiFi is connected, it will send IFTTT request once.
![pic](images/Ch3_11.png)

5. Input the following value
a.IFTTT API key: “HnXXXXXXXXXXXXXjb “. 
b.value 1-3: input value。
c.event_name: event name to trigger in Webhooks (eg. SendEmail)
![pic](images/Ch3_12.png)

6. If data is uploaded successfully, “Uploaded OK” will be shown.
![pic](images/Ch3_13.png)