# IoT:bit Introduction

## Introduction
Smarthon IoT Bit is an IoT orientated expansion board for Micro:bit. With the help of this, Micro:bit able to connect to different sensors or actuators without welding and start to use the internet services. 
<P>
It provides 13 regular GVS socket, allow user to connect batch of sensors at the same time to receive group of data. For some special purpose sensors/actuator, such distance sensor, motor and OLED display, an independent socket are offered, so not only the digital and analog I/O device can use in project, but also I2C device become an option to the Micro:bit from now on. Last but not least, a buzzer is built-in on the board to provide sound generation.
<P>
Several of wireless modules are compatible with the Smarthon IoT Bit, such Bluetooth and Wi-Fi modules. Beside of the commonly used Wi-Fi module ESP8266, the advanced version ESP32 is available to use on the IoT Bit too. After connect to internet, user able to enjoy the abundant internet resource to create the IoT project.
<P>

![pic_600](images/iot_image00.png)

## Features
* Exchangeable wireless modular design (ESP8266, ESP32, BLE)
* Extended I/O pin from Mirco:bit with GVS socket
* Independent socket for OLED screen, Distance sensor and Motor
* Separate Servo pin from ESP module
* On board Buzzer with on/off switch
* Various types of power supply (USB, XH2.54 battery port, DC jack) 

## Hardware Size

Product size: 75mm X 65mm X 20mm
PCB thinkness: 1.5mm
Hole diameter: 4mm

![pic_600](images/iot_image01.png)

## Specification

|Item|Parameters|Remarks|
|--|--|--|
|Size|75mm X 65mm X 20mm| Without Packing|
|Power supply| USB:5V 0.5A <BR> XH2.54 Battery port:3.7~6V 1A <BR>DC 5.5mm:3.7~6V 1A|Maximun current limit<BR> of whole board: 1A |
|Operation Temperature|-25 to 80℃||
|Buzzer|Passive Buzzer(Musical)||
|Wireless Module|ESP8266<BR>ESP32<BR>Bluetooth|Operate under UART protocol|
|OLED Module|128*64 resolution OLED<BR> Screen SSD1306|Operate under I2C protocol|
|Mirco:bit lead out|13 I/O Pins<BR>(13 Digital & AnalogOut Pins)<BR>(6 AnalogIn Pins)|<B>Reserved Pins:</B><BR>Wireless module:P8,P16<BR>Distance Sensor:P14,P15<BR>Motor:P12,P13|
|I2C Pins|P19,P20|3 available ports,<BR>1 port reserved for OLED|
|ESP lead out|3 Pins for servo control(S1,S2,S3)|Control by ESP chip|
|Net weight|||


## Hardware Interface
![pic_600](images/iot_image02.png)

* 1.Micro:bit edge connecter
* 2.USB power supply port
* 3.Power Switch
* 4.XH2.54 Battery port
* 5.DC Battery port
* 6.Wireless Module socket
* 7.I2C connection port(1 reserved for OLED)
* 8.GVS I/O Pins Lead Out
* 9.Buzzer /w Switch
* 10.Motor port
* 11.ESP Servo port
* 12.Distance Sensor port
* 13.QuickAccess GVS port

## Pinout Diagram
![pic_700](images/iot_image03.png)
Please open the image in the new tab for full size

## Detail Hardware Description

<B>Mirco:bit edge connecter</B>
![pic](images/iot_image04.png)
Provide the socket for the Micro:bit to install. Follow the instruction icon right about that to install the Micro:bit to the expansion board.

<B>Power port(USB, Battery, DC) & Switch</B>
![pic](images/iot_image05.png)
Provide three different type of methods to power on the expansion board and Mirco:bit. User can either choose common 5V USB power, or two different port which connect to 3.7V ~ 6V battery box. 

<B>OLED Module</B>

![pic](images/iot_image06.png)
The expansion board have the reserved space to place a SSD1306 0.96 inch OLED screen. User can use the I2C connection port to output the visual element on that module.

<B>Wireless Module</B>
![pic](images/iot_image07.png)
The Wireless Module provide the Core function of the expansion board. Though different modules install on the socket, Mirco:bit gain the correspond connectivity ability. User may install ESP32, ESP8266, Bluetooth to implement various application project, make use of the IoT resource.

<B>ESP Servo port</B>
![pic](images/iot_image08.png)
When installed the ESP32 module, it provide extra 3 servo control port to connect the Servo motor. Compatible with general GVS 180/360 Servo motor (SG90/SG90S)

<B>Micro:bit lead out Pins</B>
![pic](images/iot_image09.png)
The Lead Out from the Mirco:bit I/O pins, provide great expansion feature for the Mirco:bit , user can connect up to 13 different sensor/actuator at the same time. Each independent GVS socket make the connection become more connivance. 

<B>Buzzer & Switch</B>
![pic](images/iot_image10.png)
The IoT Bit built-in a Passive Buzzer on the board, which connected to P0. Using the program can generate different tone of sound. With the switch, it can have manual control to the audio.

<B>QuickAccess GVS connecter</B>
![pic](images/iot_image11.png)
To some GVS sensor which provide the Quick Insert Pin, it can use on the QuickAccess GVS connecter. It do not need to use the cable to connect the sensor, simplify the product in the application.

<B>Distance Sensor port</B>
![pic](images/iot_image12.png)
On the IoT Bit, a port is reserved for the HC-SR04 Distance Sensor. Whether use multi separate cable to connect two data pin, user can use a 4 pin connection cable to join the sensor and Mirco:bit. The two data pins in this port is p14 and p15 respectively.

<B>Motor port</B>
![pic](images/iot_image12_5.png)
Beside the 3pin single direction DC motor, IoT Bit is compatible with the 4pin bi-direction dc motor. User can use a 4pin connection cable to control the 4pin motor.
The two data pins in this port is p12 and p13 respectively. 

## Software Support

<B>MakeCode editor</B>

The MakeCode editor is the official cross-platform editor designed for BBC Mirco:bit, it is available on Web Browser, Mobile and tablets Apps. The Colorful coding block is familiar to who previously used Scratch, providing a simple and clear way to programming on the Micro:bit.<P>
The editor offer a text-based mode for user to programming using JavaScript rather than drag the blocks<BR>
[MakeCode](https://makecode.microbit.org/#editor)
![pic_700](images/iot_image13.png)

<B>Python editor</B><P>
Python is one of the most famous programming language, widely used in school and industry. Micro:bit provided an online python editor for user to study and exercise python on Micro:bit. User just need to connect Mirco:bit with USB and click the Flash button, the compile and upload progress will be finish automatically. <BR>
[Python editor](https://python.microbit.org/v/2.0)
![pic_700](images/iot_image14.png)


