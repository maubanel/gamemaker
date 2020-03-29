---
layout: default
title:  "Moving 3 Ways Part I"
---


_____ 

## Part 3 - Dots and Speed

_____ 

### Dots
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create a new **Sprite** and call it `sDot`.  Make it `32` by `32` pixels:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DotSprite.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Draw with the circle fill tool and a white palette a 8 pixel radius dot:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/8PixelDot.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create another `32` by `32` sprite called `sDotLarge`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/sDotLargeSprite.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Draw with the circle fill tool and a white palette and fill 95% of the sprite:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/sLargeDotDraw.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We need to create a new **Object** and asign `sDot` and call it `oDot`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/oDotCreate.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We need to create another new **Object** and asign `sDotLarge` and call it `oDotLarge`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/oDotLargeCreate.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Instead of placing each dot in the room that would take a long time we can use the array in `oGameManager` to in code create the dots. Create a new script called `ResetDots` and make a two dimensional for loop and we can `instance_create_depth` the dots on screen:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DotScriptSmallDots.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call this from the `oGameManager` **Create Event**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DotScriptSmallDotsB.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the game and this is what it should look like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SmallDotsInGame.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now add the large dots by looking for the number `2` in the array:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DotScriptAllDots.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the game and this is what it should look like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AllDotsInGame.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. PacMan moves at different speeds 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AllDotsInGame.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

### Speed
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. PacMan runs at `80`% speed in normal (no dots) and 71% speed over dots.  Lets add to the global variables.  But this time we will dot reference to them and make them local, which is a better best practice:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewNormalSpeedVairables.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Since Pac Man will have different speeds we need a variable to keep track of this.  Lets create a new variable called `CurrentSpeed` for PacMan:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewSpeedVariablePacMan.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now carefully go through the scripts and replace `global.Speed` with `CurrentSpeed`.  First edit PacMan Create and change:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChangeGlobalToCurrent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets change it to CurrentSpeed in lateral movement script:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LatCurrSpeedA.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. and:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LatCurrSpeedB.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets change it to CurrentSpeed in the turning script:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveTurnCurrSpeed.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. and:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveTurnCurrSpeedB.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. and:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveTurnCurrSpeedC.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets clamp the square we are on so we don't go out of bounds on the array.  Then lets store a variable with the current square type we are over.  Then set the speed variable to the correct one that the player is over.  First open `UpdateGridPosition` and clamp value:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ClampUpgradeGridPos.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now update the Pac Step Event:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ClampAndSetSpeed.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

### Eating Dots
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now Pac Man should consumer the dots when going over them.  Lets only deal with the small dots and only do the large one when we have enemies to eat.  So when Pac Man leaves leaves the square it should consumer the dot. Add two variables to `oPacMan`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LastGridXAddVar.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now update the last frames position in UpdateGridPosition:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddLastGridToUpdateGridPos.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create a new script called `PacEatsDots` .  Check to see if the new grid is different than the last grid.  If it is then consume the dot and update the grid so that if this player moves over the space again he will move at his normal and not dot speed.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/EatDotUpdateGrid.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call it in Pac's step event:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacStepEatDots.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 


<br />  
<br />  
[<- Previous](PacManStyleGame_5.html)&nbsp;&nbsp;&nbsp;[Home](../../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](PacManStyleGame_7.html)
<br />  
<br />  
<br />  
<br />  