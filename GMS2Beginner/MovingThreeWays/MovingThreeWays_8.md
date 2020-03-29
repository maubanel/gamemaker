---
layout: default
title:  "Moving 3 Ways Part VIII"
---

## Syntax Used  
___ 
### GameMaker Variables  

<div class="table table-striped">
<div markdown = "1">

| Variable | Description |
| -------- | -------- |
| ``` x ```  | is a variable that each object inherits that represents the location on the x-axis in the [cartesian coordinate system](../CoordinateSystems/CartesianCoordinateSystem.html)  |
| ``` y ```   | is a variable that each object inherits that represents the location on the y-axis in the [cartesian coordinate system](../CoordinateSystems/CartesianCoordinateSystem.html)  |
| ``` hspeed ```   | is a physics property representing the number of pixels per second along the horizontal axis.  There is no friction in GameMaker by default so this can be set once in the **_Create Event_**    |
| ``` vspeed ```   | is a physics property representing the number of pixels per second along the vertical axis.  There is no friction in GameMaker by default so this can be set once in the **_Create Event_**       |
| ``` image_angle ```   | represents in degrees (0&deg;  to 360&deg;) the angle the sprite is pointing in.  The default setting is 0&deg; (or to the right)  |
| ``` direction ```   | represents in degrees (0&deg;  to 360&deg;) the motion vector that the motion in moving in.  Is often used in conjunction with speed  |
| ``` speed ```   | represents the speed (regardless of angle) in terms of pixels per second   |



</div>
</div>
<div markdown = "1">
___ 
### GameMaker Functions 
</div> 
<div class="table table-striped">
<div markdown = "1">



| Function | Description |
| -------- | -------- |
| ``` keyboard_check(key) ```  | Is a function that takes a single parameter (the key or mouse button or joystick button pressed).  The function returns a ``` true ``` or ``` false ``` depending on whether that button is in the pressed state or not. Example `if (keyboard_check(vk_up)) { y = y - 10;}` |



</div>
</div>

<div markdown = "1">
___ 
### Concepts Introduced 

* [Variables](../ProgrammingConcepts/Variables.html)
* [Functions](../ProgrammingConcepts/Functions.html)
* [Naming Convention](../Misc/NamingConvention.html)
* [Cartesian Coordinate System](../CoordinateSystems/CartesianCoordinateSystem.html)
* [Polar Coordinate System](../CoordinateSystems/PolarCoordinateSystem.html)
* [Conditional if (true) { do something ... } Statements](../ProgrammingConcepts/Conditional-If.html)


[<- Previous](MovingThreeWays_7.html)&nbsp;&nbsp;&nbsp;[Home](../../index.html)
</div>
<br />  
<br />  
<br />  
<br /> 