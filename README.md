# Line Following Robot
>This is a guide to mechanism and building of line following robots.

#### Pre-requisites: None

## What is a Line Following Bot?
A line following robot is a type of mobile robot that is designed to follow a predetermined path, typically a line or a series of lines, using sensors to detect the line's position and adjust its movement accordingly. The robot typically uses infrared or optical sensors to detect the line and then uses that information to control its movement, either by adjusting the speed or direction of its wheels or by adjusting the position of its body. The goal of a line following robot is to follow the line as accurately and efficiently as possible, without deviating from the path or getting stuck. They are widely used in various industries like material handling and manufacturing, as well as in research and educational settings.

> In this guide we will be discussing about LFR that uses **IR sensors and differential drive mechanism** for mobolity.

## Logic
### Basic Approach:
When the line is detected exactly below the bot, the bot keeps moving forward. If the line is detected to be off-centred to the left or right, the bot turns in the respective direction.

```
if line at centre 
    move(forward)
if line at left
    move(left)
if line at right
    move(right)
```
> One can have rate of turning just based on whether line on left or right or different rates of turning based on factors like current and past positions of the line.
 
## Sensing and Detection 

As mentioned above, the line will be detected with use of IR sensors.

### Power supply to the sensors:
   
Widely used IR sensors have 3 pins, namely, `GND` (Ground), `VCC`(Supply) and `OUT`(Output). The sensors operate at `VCC` connected to 5V.

> Refer [this link](https://www.google.com/) for working of the sensors.

### Output:
The sensors return a value denoting whether the IR rays are reflected back.The sensors can give both `digital` outputs. In case of arduino, using `digitalRead()` gives the value `0` and `1` if an obstacle (or white area in this case) is present or not respectively.


### Interpreting the outputs:
> Usually, two sensors are used in basic implementation. We will also look in the case where five sensors are used.
#### When two sensors are used:
> The width of line to be followed is considered to be lesser than distance between sensors.

When no sensors detect line, line is between both the sensors and hence aligned with the bot.
When only left sensor detects the line, the line is on left of the bot.
When only right sensor detects the line, the line is on right of the bot.

[IMAGE TO BE ADDED]


#### When five sensors are used:
> The width of line to be followed is considered to be lesser twice than distance between consecutive sensors.

[IMAGE TO BE ADDED]

## Flow of Power
```mermaid
graph TD;
    Battery-->MotorDriver;
	MotorDriver-->Motors;
	MotorDriver-->Arduino;
	Arduino-->IRSensors;
```
All components except IR sensors are powered with the voltage delivered by the battery whereas the IR sensors are powered by 5V from Arduino.
The `5V` pins in Arduino are connected to VCC of the sensors.

> `Arduino UNO` has only one `5V` pin. Hence, when using independent sensors set some `GPIO` pins in Arduino to `HIGH` and use them to derive the power

## Flow of Signal
```mermaid
graph TD;
	IRSensors --> Arduino;
	Arduino --> Processing;
	Processing --> Command;
	Command --> MotorDriver;
```
Arduino reads and interprets the readings from arduino as decribed above and gives an output command to the motor driver that runs the motors accordingly.

## Actuation

## PID Control
