---
layout: default
title:  "Space Rocks Extended Part III"
---

## Syntax Used  
___ 
### GameMaker Variables 
___ 
<div class="table table-striped">
<div markdown = "1">


| Variable | Description |
| -------- | -------- | 
| ``` x ```  | is a public variable that each object inherits that represents the location on the x-axis in the [cartesian coordinate system](CaretesianCoordinateSystem.md) |
| ``` y ```   | is a public variable that each object inherits that represents the location on the y-axis in the [cartesian coordinate system](CaretesianCoordinateSystem.md) |
| ``` image_angle ```   | represents in degrees (0&deg;  to 360&deg;) the angle the sprite is pointing in.  The default setting is 0&deg; (or to the right) |
| ``` direction ```   | represents in degrees (0&deg;  to 360&deg;) the motion vector that the motion in moving in.  Is often used in conjunction with speed |
| ``` speed ```   | represents the speed (regardless of angle) in terms of pixels per second |
| ``` room_width ```   | the width of the current room in pixels |
| ``` room_height ```   | the height of the current room in pixels |
| ``` image_speed ```   | the speed with which the image_index is changed |
| ``` image_index ```   | the current sub-image being shown for the instance sprite |
| ``` object_index ``` | Returns the index number of the object that the instance has been made from.|
| ``` timeline_index ``` | Returns the time line index for the instance. |
| ``` timeline_running ``` | boolean that sets a time line to run or stop. |



</div>
</div>
___ 
### GameMaker Functions
<div class="table table-striped">
<div markdown = "1">


| Variable | Description |
| -------- | -------- | 
| ``` keyboard_check(key) ```  | Is a function that takes a single parameter (the key or mouse button or joystick button pressed).  The function returns a ``` true ``` or ``` false ``` depending on whether that button is in the pressed state or not. Example: ``` if (keyboard_check(vk_up)) { y = y - 10; } ``` |
| ``` move_wrap(hor, vert, margin) ``` | Wraps the player around the room if relevant.  Include in a **_step event_** |
| ``` motion_add(dir, speed) ``` | This function adds to the direction and a movement speed of an instance, and can be very useful for simple physics. |
| ``` clamp (val, min, max) ``` } | With this function you can maintain an input value between a specified range. Example: ``` speed = clamp(speed, 1, 10); ``` |
| ``` instance_create(x, y, obj) ``` | Creates an instance of a given object at a given position. Returns index of newly created instance. | 
| ``` instance_destroy() ``` | Destroys the calling instance, removing it from the room. | 
| ``` game_restart() ``` | Restarts the game. |
| ``` timeline_running() ``` | Sets a time line to run or stop. |


___ 
### Concepts Introduced  
* [Adding Two Vectors](../FirstGame/SpaceRocks_2.html#adding-two-vectors) 
* [Creating a new Object Instance](../FirstGame/SpaceRocks_3.html#creating-a-new-object-instance)  
* [Compound Logical Operators](../FirstGame/SpaceRocks_3.html#compound-logical-operators) 
* [Parent / Child Hierarchy](../FirstGame/SpaceRocks_4.html#parent--child-hierarchy)  
* [Collision Event](../FirstGame/SpaceRocks_4.html#collision-event)  
* [With Other](../FirstGame/SpaceRocks_5.html#with-other)  
* [Alarms](../FirstGame/SpaceRocks_4.html#alarms)  
* [Timelines](SpaceRocksExtended_2.html#timelines)  

___ 
<br /><br>

[<- Previous](SpaceRocksExtended_2.html)&nbsp;&nbsp;&nbsp;[Home](../README.md)  

<br />  
<br />  
<br />  
<br /> 