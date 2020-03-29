---
layout: default
title:  "Moving 3 Ways Part I"
---


_____ 

### Turning
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets create a boolean called `IsTurning` on PacMan:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/IsTurningBoolean.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Lets have two variables that keep the values for how much before and after we are looking for:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TurnRightLeftSpace.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Create a new script called `PacManMoveTurn`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacManMoveTurn.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 


<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Call it from the Step Event in Pac-Man:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CallPacManMoveTurn.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Add logic to turn down and enter turning mode:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Phase1TurningDown.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now the problem is that you can turn on any square like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TurnBadInGame.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  We need to check if that grid is open to move in. Lets create a new function called `CanMoveToGrid`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CanMoveToGrid.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Add that check to `PacManMoveTurn`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddDownCheck.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Don't move laterally while turning:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NoTurnLateral.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 


<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Repeat for turning up:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Phase1TurningUp.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Add offset for y axis:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpaceUpAndDown.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.   Repeat for turning left:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Phase1TurningLeft.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.   Repeat for turning right:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Phase1TurningRight.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Before entering phase 2, we run a large else after is IsTurning is true.  We offset the location of x to halfway to the end point.  We move up or down by a speed amount.  We add to `IsTurning` and increment it to phase 3
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddPhase2TurnUpDown.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  We now at the end have an if and move the sprite halfway to its goal:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GoIntoPhase2A.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  We now at the end have an if and move the sprite halfway to its goal:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GoIntoPhase2A.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Finish for other pase and up IsTurning to move into mode 3:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GoIntoPhase2B.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Fix IfSpaceFreeToMove to only freeze if past center:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FixIfSpaceFreeToMove.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  and:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FixIfSpaceFreeToMoveB.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Phase 3, set `keyboard_lastkey`, place player in center of  `x`, adjust speed and turn `IsTurning` to false.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddPhase3TurnUpDown.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Repeat for horizontal:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Phase2And3LeftRightB.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<br />  
<br />  
[<- Previous](PacManStyleGame_3.html)&nbsp;&nbsp;&nbsp;[Home](../../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](PacManStyleGame_5.html)
<br />  
<br />  
<br />  
<br />  