# Project 3:  Control Multiple Actuators Lv2
Level: ![level](images/level3.png)
## Part List
1. Mono-tone buzzer X1 (placed on Multiple Actuators for smart house)
2. Multiple Sensors for smart house X1
3. Multiple Actuators for smart house X1
4. Connecting Wire X1
5. micro:bit X1
6. USB Cable X1

## Description
In project 3, this is level two to control multiple actuators and you can learn how to use micro:bit on shake to control mono-tone buzzer on and off together.

## Steps
1. Basic (Add block on start) > House (Add block Initialize Smarthon multiple-sensor)
2. Variables (Make a Variable “Buzzer On”) > Variables (Add block set item to 0, change “item” to “Buzzer On”; “0” to Logic “false”)
3. Input (Add block on shake)
4. Logic (Add block if…then…else) > For if : Logic (Add block 0 = 0, change “0” to Variables “Buzzer On”; “0” to Logic “false”)
5. For then: House-More (Add block Set Buzzer to intensity 0, change “0” to “1023”) > Variables (Add block set item to 0, change “item” to “Buzzer On”; “0” to Logic “true”) > Basic (Add block show icon, change “heart” to “yes”)
6. For else: House-More (Add block Set Buzzer to intensity 0) > Variables (Add block set item to 0, change “item” to “Buzzer On”; “0” to Logic “false”) > Basic (Add block show icon, change “heart” to “no”)
![auto_fit](images/P3_1.png)
![auto_fit](images/P3_3.png)

## Hardware
7. **Download** the code and transfer to micro:bit
8. Plug the micro:bit into Multiple Sensors
9. Connect Multiple Sensors and Multiple Actuators by connecting wire
10. Shook the micro:bit to turn on/off the buzzer
![auto_fit](images/P3_4.png)
<span id="remarks" >* Try to use on shake to turn on/off other actuators. </span>

