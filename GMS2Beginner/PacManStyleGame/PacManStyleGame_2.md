---
layout: default
title:  "Moving 3 Ways Part I"
---


_____ 

### Position and Move Along Center
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets add an offset of 16 to `oGameManager`'s variables:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/oPacManVariables.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Unhardcode variables in `oGameManager` create event:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacManCreateFirst.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Run the game, it should look like this and PacMan is now aligned to eat pills in center of squares:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AlignedPacMan.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 


<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Create a new script and we will use this every time we want to reset pac-man to the begining.  Lets call it `ResetPacManToStart` and add the position and make it point left as this is the direction that Pac starts in:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RestPacManToStart.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 


<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Add a **Create Event** and call the above script:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ResetPacManToStart.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Run the game now Pac Man faces left:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacLeftInGame.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now we want PacMan to move.  But all moving characters including the ghosts will be based off of the same speed.  Oopen `oGameManager` and create a variable alled `Speed` and set default to `10`.  Note the capital S:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/globalSpeedSetGameManager.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 


<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Edit `oPacMan` create event and add:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpeedAndDirecitonForPac.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Run the game, Pac Man should move off the screen to the left:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacManMovingToLeft.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now lets screen wrap Pac-Man so that when it goes through the tunnel, it will go from left to right and right to left.  There is a GameMaker function called `move_wrap()` that we will use.  Open `oPacMan` and create a **Step Event**. Run the game and Pac Man now wraps and moves left endlessly.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveWrapHoriz.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  To now figure out which square PacMan occupies, we need to first know where the center of our character is located. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MiddleCenter.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now we need to see what `x` and `y` position we are in the world.  We can print to the console to expose this.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ShowDebugMessagePacPos.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Create  a script to return the Grid Number (starting at 0).  Call it `GetGridNum`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetGridNumScript.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Find out what grid position pac-man occupies.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TopLeftCornerDebug.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  We need to track this so lets create a variable to hold these values.  Open `ObjPacMan` and add the following variables:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GridXGridYPacMan.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Create a new script that updates what grid position pac is in:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetGridPosition.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now adjust the **Step Event** to record these values and alter the debug code:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GridSizeVariablePacMan.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Lets now draw a square to show what position Pac Man occupies.  Lets add a **Draw Event**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacManDebugDraw.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now add code to draw a rectangle:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacDebugDrawCode.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Run the game and you can see the square changes.  To see it more explicitly change the speed to 1 in the `GameManager` object:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GlobalSpeed1.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<br />  
<br />  
[<- Previous](PacManStyleGame_1.html)&nbsp;&nbsp;&nbsp;[Home](../../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](PacManStyleGame_3.html)
<br />  
<br />  
<br />  
<br />  