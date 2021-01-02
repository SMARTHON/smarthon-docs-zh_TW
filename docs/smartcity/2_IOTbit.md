# IoT:bit Introduction

## Introduction
Smarthon IoT Bit is an IoT orientated expansion board for Micro:bit. With the help of this, Micro:bit able to connect to different sensors or actuators without welding and start to use the internet services. 
<P>
It provides 13 regular GVS socket, allow user to connect batch of sensors at the same time to receive group of data. For some special purpose sensors/actuator, such distance sensor, motor and OLED display, an independent socket are offered, so not only the digital and analog I/O device can use in project, but also I2C device become an option to the Micro:bit from now on. Last but not least, a buzzer is built-in on the board to provide sound generation.
<P>
It is the most powerful Wi-Fi extension board for micro:bit in the STEM community. The core is using dual core processor ESP32 compared with the ESP8266 which is single core processor. Besides of the basic ThingSpeak and IFTTT Web services, it supports Wide Area Network (WAN) and can be controlled by mobile app, Amazon echo dot and Google home remotely. Also, it supports object to object communication (O to O) in the Internet. It can facilitate the students to learn the communication between the objects.
<P>

![auto_fit](images/2_IOT/iot_image00.jpg)



## Product Features

![auto_fit](images/2_IOT/iot_image005.jpg)


* The Most powerful IoT chip ESP32 embedded for micro:bit
* Exchangeable wireless modular design (ESP8266, ESP32, BLE)
* Integrated OLED and Onboard buzzer embedded
* Extended I/O port x13, I2C port x2 from mirco:bit with GVS socket
* Extended Servo port x3 from ESP module 
* Various types of power supply (USB, 3.7V lithium battery, 6V Normal battery)
* Extra Port: Crocodile Pin, Quick Access Port and 4-Pin Port for different usage


## Hardware Size

Product size: 75mm X 65mm X 20mm<BR>
PCB thinkness: 1.5mm<BR>
Hole diameter: 4mm<BR>

![auto_fit](images/2_IOT/iot_image01.png)

## Specification

|Item|Parameters|Remarks|
|--|--|--|
|Size|75mm X 65mm X 20mm| Without Packing|
|Power supply| USB:5V <BR> Lithium Battery :3.7~4.2V <BR>AA Battery*4 :6V |Maximun current limit<BR> of whole board: 1A |
|Operation Temperature|0 to 80℃||
|Buzzer|Passive Buzzer(Musical)||
|Wireless Module|ESP8266<BR>ESP32<BR>Bluetooth|Operate under UART protocol|
|OLED Module|128*64 resolution OLED<BR> Screen SSD1306|Operate under I2C protocol|
|Mirco:bit lead out|13 I/O Pins<BR>(13 Digital & AnalogOut Pins)<BR>(6 AnalogIn Pins)|<B>Reserved Pins:</B><BR>Wireless module:P8,P16<BR>4-Pins module:P12,P13|
|I2C Pins|P19,P20|3 available ports,<BR>1 port reserved for OLED|
|ESP lead out|3 Pins for servo control(S1,S2,S3)|Control by ESP chip|



## Pinout Information
<H3>Pinout Diagram:</H3><BR>
![auto_fit](images/2_IOT/iot_image03.png)<P>
<H3>Port Diagram:</H3><BR>
![auto_fit](images/2_IOT/iot_image006.png)
<P>
Please open the image in the new tab for full size
<P>
<H3>Pinout Table</H3>

<div style="overflow-x: scroll;">
<style type="text/css">
::-webkit-scrollbar {
    width: 0px;  /* Remove scrollbar space */
    background: transparent;  /* Optional: just make scrollbar invisible */
}
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-ux7d{background-color:#c0c0c0;border-color:#000000;font-family:Arial, Helvetica, sans-serif !important;;text-align:center;
  vertical-align:middle}
.tg .tg-l89d{border-color:#000000;font-family:Arial, Helvetica, sans-serif !important;;text-align:center;vertical-align:middle}
.tg .tg-j1bp{background-color:#efefef;border-color:#000000;font-family:Arial, Helvetica, sans-serif !important;;text-align:center;
  vertical-align:middle}
</style>
<table class="tg" style="undefined;table-layout: fixed; width: 599px">
<colgroup>
<col style="width: 98.008404px">
<col style="width: 80.008404px">
<col style="width: 85.004202px">
<col style="width: 101.004202px">
<col style="width: 235.004202px">
</colgroup>
<thead>
  <tr>
    <th class="tg-ux7d">Type</th>
    <th class="tg-ux7d"></th>
    <th class="tg-ux7d">Mirco:bit</th>
    <th class="tg-ux7d">IoT:bit</th>
    <th class="tg-ux7d">Extra Port</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-l89d" rowspan="6">Analog</td>
    <td class="tg-l89d">P0</td>
    <td class="tg-l89d"></td>
    <td class="tg-l89d">Buzzer</td>
    <td class="tg-l89d">Rapid Access Port</td>
  </tr>
  <tr>
    <td class="tg-j1bp">P1</td>
    <td class="tg-j1bp"></td>
    <td class="tg-j1bp"></td>
    <td class="tg-j1bp">Rapid Access Port</td>
  </tr>
  <tr>
    <td class="tg-l89d">P2</td>
    <td class="tg-l89d"></td>
    <td class="tg-l89d"></td>
    <td class="tg-l89d">Rapid Access Port</td>
  </tr>
  <tr>
    <td class="tg-j1bp">P3</td>
    <td class="tg-j1bp">LED</td>
    <td class="tg-j1bp"></td>
    <td class="tg-j1bp"></td>
  </tr>
  <tr>
    <td class="tg-l89d">P4</td>
    <td class="tg-l89d">LED</td>
    <td class="tg-l89d"></td>
    <td class="tg-l89d"></td>
  </tr>
  <tr>
    <td class="tg-j1bp">P10</td>
    <td class="tg-j1bp">LED</td>
    <td class="tg-j1bp"></td>
    <td class="tg-j1bp"></td>
  </tr>
  <tr>
    <td class="tg-l89d" rowspan="6">Digital</td>
    <td class="tg-l89d">P6</td>
    <td class="tg-l89d">LED</td>
    <td class="tg-l89d"></td>
    <td class="tg-l89d"></td>
  </tr>
  <tr>
    <td class="tg-j1bp">P9</td>
    <td class="tg-j1bp">LED</td>
    <td class="tg-j1bp"></td>
    <td class="tg-j1bp"></td>
  </tr>
  <tr>
    <td class="tg-l89d">P12</td>
    <td class="tg-l89d"></td>
    <td class="tg-l89d"></td>
    <td class="tg-l89d">4-Pin Port</td>
  </tr>
  <tr>
    <td class="tg-j1bp">P13</td>
    <td class="tg-j1bp">SPI(SCK)</td>
    <td class="tg-j1bp"></td>
    <td class="tg-j1bp">4-Pin Port</td>
  </tr>
  <tr>
    <td class="tg-l89d">P14</td>
    <td class="tg-l89d">SPI(MISO)</td>
    <td class="tg-l89d"></td>
    <td class="tg-l89d">4-Pin Port</td>
  </tr>
  <tr>
    <td class="tg-j1bp">P15</td>
    <td class="tg-j1bp">SPI(MOSI)</td>
    <td class="tg-j1bp"></td>
    <td class="tg-j1bp">4-Pin Port</td>
  </tr>
  <tr>
    <td class="tg-l89d" rowspan="2">Serial</td>
    <td class="tg-l89d">P8</td>
    <td class="tg-l89d">UART(TX)</td>
    <td class="tg-l89d">ESP32(RX)</td>
    <td class="tg-l89d"></td>
  </tr>
  <tr>
    <td class="tg-j1bp">P16</td>
    <td class="tg-j1bp">UART(RX)</td>
    <td class="tg-j1bp">ESP32(TX)</td>
    <td class="tg-j1bp"></td>
  </tr>
  <tr>
    <td class="tg-l89d" rowspan="2">I2C</td>
    <td class="tg-l89d">P19</td>
    <td class="tg-l89d">I2C</td>
    <td class="tg-l89d">OLED(SCL)</td>
    <td class="tg-l89d"></td>
  </tr>
  <tr>
    <td class="tg-j1bp">P20</td>
    <td class="tg-j1bp">I2C</td>
    <td class="tg-j1bp">OLED(SDA)</td>
    <td class="tg-j1bp"></td>
  </tr>
  <tr>
    <td class="tg-l89d" rowspan="3">External<br>Servo</td>
    <td class="tg-l89d">S1</td>
    <td class="tg-l89d"></td>
    <td class="tg-l89d">ESP32(23)</td>
    <td class="tg-l89d"></td>
  </tr>
  <tr>
    <td class="tg-j1bp">S2</td>
    <td class="tg-j1bp"></td>
    <td class="tg-j1bp">ESP32(22)</td>
    <td class="tg-j1bp"></td>
  </tr>
  <tr>
    <td class="tg-l89d">S3</td>
    <td class="tg-l89d"></td>
    <td class="tg-l89d">ESP32(21)</td>
    <td class="tg-l89d"></td>
  </tr>
</tbody>
</table>
</div>
<P>


## Hardware Interface

![pic](images/2_IOT/iot_image02.jpg)

1. Mirco:bit edge connecter
2. USB Port 
3. Power Switch
4. 3.7V Lithium battery Port [XH2.54] 
5. 6V 4*AA(1.5V) battery Port [DC 5.5mm] 
6. Rapid Access Port
7. Crocodile Pin
8. I2C Port
9. 4-Pins Port
10. ESP Servo Port
11. Buzzer switch
12. 4mm Hole
13. OLED Module (128*64 pixel)
14. ESP32 Wireless Module
15. Buzzer
16. General GVS Port


## Detail Hardware Description

<H3>Mirco:bit edge connecter</H3><BR>
![pic](images/2_IOT/iot_image04.png)
<P>Provide the socket for the Micro:bit to install. Follow the instruction icon right about that to install the Micro:bit to the expansion board.

<H3>Power port(USB, Battery, DC) & Switch</H3><BR>
![pic](images/2_IOT/iot_image05.png)
<P>Provide three different type of methods to power on the expansion board and Mirco:bit. User can either choose common 5V USB power, or two different port which connect to 3.7V ~ 6V battery box. 

<H3>OLED Module</H3>

![pic](images/2_IOT/iot_image06.png)
<P>The expansion board have the reserved space to place a SSD1306 0.96 inch OLED screen. User can use the I2C connection port to output the visual element on that module.

<H3>Wireless Module</H3><BR>
![pic](images/2_IOT/iot_image07.png)
<P>The Wireless Module provide the Core function of the expansion board. Though different modules install on the socket, Mirco:bit gain the correspond connectivity ability. User may install ESP32, ESP8266, Bluetooth to implement various application project, make use of the IoT resource.

<H3>ESP Servo port</H3><BR>
![pic](images/2_IOT/iot_image08.png)
<P>When installed the ESP32 module, it provide extra 3 servo control port to connect the Servo motor. Compatible with general GVS 180/360 Servo motor (SG90/SG90S)

<H3>Micro:bit lead out Pins</H3><BR>
![pic](images/2_IOT/iot_image09.png)
<P>The Lead Out from the Mirco:bit I/O pins, provide great expansion feature for the Mirco:bit , user can connect up to 13 different sensor/actuator at the same time. Each independent GVS socket make the connection become more connivance. 

<H3>Buzzer & Switch</H3><BR>
![pic](images/2_IOT/iot_image10.png)
<P>The IoT Bit built-in a Passive Buzzer on the board, which connected to P0. Using the program can generate different tone of sound. With the switch, it can have manual control to the audio.

<H3>Rapid Access Port</H3><BR>
![pic](images/2_IOT/iot_image11.png)
<P>To some GVS sensor which provide the Rapid Insert Pin, it can use on the Rapid Access Port. It do not need to use the cable to connect the sensor, simplify the product in the application.

<H3>4-Pins Module port</H3><BR>
![pic](images/2_IOT/iot_image12.png)
<P>On the IoT Bit, two ports are reserved for the 4 Pins Module. Each port can connect to some sensors or actuators which required use two I/O Pins at the same time, such Distance Sesnor and Motor. In total, there are 4 I/O Pins being used, they are P12, P13, P14, P15 respectively.

<H3>Crocodile Pin</H3><BR>
![pic](images/2_IOT/iot_image12_5.png)
<P>For the user who use the crocodile cable clips to connect parts, Iot Bit reserved 5 Pins for them to get easier access. There are 3 Pins from GVS Port 0,1,2 and 2 Pins for 3V and Ground.
<P>

## Software Support

<H3>MakeCode editor</H3>

The MakeCode editor is the official cross-platform editor designed for BBC Mirco:bit, it is available on Web Browser, Mobile and tablets Apps. The Colorful coding block is familiar to who previously used Scratch, providing a simple and clear way to programming on the Micro:bit.<P>
The editor offer a text-based mode for user to programming using JavaScript rather than drag the blocks<BR>
[MakeCode](https://makecode.microbit.org/#editor)
![auto_fit](images/2_IOT/iot_image13.png)

<H3>Python editor</H3><P>
Python is one of the most famous programming language, widely used in school and industry. Micro:bit provided an online python editor for user to study and exercise python on Micro:bit. User just need to connect Mirco:bit with USB and click the Flash button, the compile and upload progress will be finish automatically. <BR>
[Python editor](https://python.microbit.org/v/2.0)
![auto_fit](images/2_IOT/iot_image14.png)


## Quick Start

<H4>1.Plug the Mirco:bit(with Program) into the the slot</H4><P>

>![auto_fit](images/2_IOT/iot_MBsolt.gif)<P>

<H4>2.Get the power supply and turn on</H4><P>

Method 1:<P>

>Plug the USB cable into the USB port and turn on the switch<P>

>![auto_fit](images/2_IOT/iot_usb.gif)<P>

Method 2:<P>

>Plug the battery case(1.5V AA*4) into the battery port and turn on the switch<P>

>![auto_fit](images/2_IOT/iot_battery.gif)<P>

Method 3:<P>

>Plug the lithium battery into the lithium battery port and turn on the switch<P>

>![auto_fit](images/2_IOT/iot_li_battery.gif)<P>

>*18650 battery holder and the battery are not included in the kit set
