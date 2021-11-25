# Project 9:  Kitchen Safety
Level: ![level](images/level3.png)
## Part List
1. Town gas sensor x 1
2. Mono-tone buzzer X1 (placed on Multiple Actuators for smart house)
3. Motor fan x 1
4. Multiple Sensors for smart house X1
5. Multiple Actuators for smart house X1
6. Connecting Wire X1
7. micro:bit X1
8. USB Cable X1

## Description
In project 9, you can learn how to use micro:bit to make Kitchen safety system. If the town gas leakage happened, the buzzer and motor fan will be turned on.

## Steps
1. Basic (Add block on start) > House (Add block Initialize Smarthon multiple-sensor)
2. Basic (Add block forever) > Logic (Add block if…then…else) > For if : Logic (Add block 0 = 0, change “0” to House “Get town gas”; “=” to “<”; “0” to “200”)
3. For then: House (Add block Set Buzzer to intensity 0)
4. For then: House (Add block Set Motor fan anti-clockwisely to intensity 0)
5. For else: House (Add block Set Buzzer to intensity 0, change 0 to 1023)
6. For else: House (Add block Set Motor fan anti-clockwisely to intensity 0, change 0 to 900)
7. Basic (Add block pause (ms) 100)
![auto_fit](images/P9_1.png)

## Hardware
8. **Download** the code and transfer to micro:bit
9. Plug the micro:bit into Multiple Sensors
10. Connect Multiple Sensors and Multiple Actuators by connecting wire
11. Connect the Motor Fan module to motor port of the Multiple Actuators and install it in the kitchen
12. You can test it by lighter
![auto_fit](images/P9_2.png)
<span id="remarks" >* Try to adjust different speed of the motor fan. </span>