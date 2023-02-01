# Line Following Robot
>This is a guide to mechanism and building of line following robots.

## What is a Line Following Bot?
A line following robot(referred as LFR from here) is a type of mobile robot that is designed to follow a predetermined path, typically a line or a series of lines, using sensors to detect the line's position and adjust its movement accordingly. The robot typically uses infrared or optical sensors to detect the line and then uses that information to control its movement, either by adjusting the speed or direction of its wheels or by adjusting the position of its body. The goal of a line following robot is to follow the line as accurately and efficiently as possible, without deviating from the path or getting stuck. They are widely used in various industries like material handling and manufacturing, as well as in research and educational settings.

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



## Sensing and Detection 

## Flow of Power

## Actuation

## PID Control
