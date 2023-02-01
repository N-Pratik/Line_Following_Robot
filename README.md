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
if line == in centre 
    move(forward)
if line == left
    move(left)
if line == right
    move(right)
```
> One can have different the rates of turning based on the position of the line
 
## Sensing and Detection 

As mentioned above, the line will be detected with use of IR sensors.

### Power supply to the sensors:
   
Widely used IR sensors have 3 pins, namely, `GND` (Ground), `VCC`(Supply) and `OUT`(Output)

## Flow of Power

## Actuation

## PID Control
