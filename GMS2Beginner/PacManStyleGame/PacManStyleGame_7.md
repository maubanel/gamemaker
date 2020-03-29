---
layout: default
title:  "Moving 3 Ways Part I"
---


_____ 

## Part 5 - Ghosts

_____ 

### Blinky
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Right click on **Sprite** and select **Create Sprite from Images".  Select the Blinky sprite provided.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateBlinkyFromImages.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call it `sBlinky` and center the origin:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/sBlinkyImportedSprite.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create a new **Object** and call it `oBlinky`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/oBlinkyObject.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Spawn Blinky in the `oGameManager` in its correct position:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BlinkyInRoom.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Since the ghost never cuts corners and always stays in the middle of lanes, lets make sure in its step event that it never leaves the center of the square.  Lets start by putting the grid size and offset in the game manager as we will use it for all the ghosts.  Open oGameManager and add `GridXNumColumns` and `GridYNumRows` to the variables:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GridSizeOffsetToGameManager.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We do not want the eyes changing unless Blinky turns.  Lets turn off animation in the create event:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StopBlinkyAnimation.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


### Pathfinding
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. The ghosts have three speeds.  Now lets make it chase Pac-Man and at the right speed by creating three new variables in `oGameManager`:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ThreeGhostSpeedVariables.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets add two more variables to the Ghosts which is their last square.  Add:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BlinkyVarsA.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets add the last grid position so we can implement the aforementioned Pathfinding logic.  We can call the `UpdateGridPosition()` that we wrote for Pac-Man on the Ghosts.  This gives us Grid, LastGrid and current grid positoin:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/UpdateGridPos.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create a new script called `oGetCenterGrid` and add:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetCenterGrid.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Since Ghosts pathfind from the grid in front of them we need to keep track of it.  Add to Blinky's variables:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NextDirectionBlinkyVar.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now add its inital direction and speed to `oBlinky`'s **Create Event**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BlinkyNextDirectionSpeed.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game and Blinky just goes off screen to the left:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BlinkyOffScreen.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We need the horizontal and vertical for the ghost and will write a custom function:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GhostHorVer.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Step Event** to the ghost and calculate its current position.  Then check whether it is Vertical or Horizontal.  This will let us know whether to check the x or y value for the center of the grid.  Stub in a comment for a function call:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GhostStepA.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create a new **Script** called GhostPathfinding.  It will have three parameters an x & y target as well as a speed.  Copy and paste our comments into it. Fill in the first section:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/InitialGhostPathfinding.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we have got to check the space from the next square.  `CanMove` won't work as it is from the current square.  We will have to duplicate it and call it `CanMoveFrom` and make the following change:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CanMoveFromScript.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to `GhostPathfinding` and add after the turn to check the regular next spaces:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NextFourDirections.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create a new **Script** called `SetNextDirection` and add the checks in order that Pac-Man wants:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetNextDirection.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets make Blinky's eyes look in the right direction.  Createa a new **Script** called `GhostDirection` and add:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GhostDirectionScript.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call this script at the end of the `oBlinky` Step Event:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CallGhostDirection.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game and basic pathfinding should work.  Ghost should be going to space 0,0 at the correct speed.  We need to add a check to pick the turn with the shortest distance to the target.  Add a call to a new script to `GhostPathfinding` script:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CallCheckFourDirections.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create a new script called `CheckFourDirections` and add:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CheckFourDirectionsA.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
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
<img src="images/CheckFourDirectionsB.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
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
<img src="images/CheckFourDirectionsC.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
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
<img src="images/CheckFourDirectionsD.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.Run the game and he should stay out of the red zone.  Add to the `GhostPathfinding`:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RedZoneNoMoveUp.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.Run the game and he should stay out of the red zone.  Now lets make it chase Pac-Man:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeBlinkyChasePac.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game and have Blinky chase you.  Over dots he should catch up, in open spaces you should be able to outrun the ghost.  Now go through the tunnel.  The Ghost doesn't wrap and it doesn't slow down.  Lets fix both those things. First the wrapping in `oBlinky`:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveWrapGhost.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Make Blinky go slow when in tunnel:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveSlowInTunnel.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the game and the player should be chased.  Run around, you should gain slightly on clear path, he should catch up to you on dotted path. He should not go up in red zone and he shouldn't go through tunnel at full speed.

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BlinkyBasicsInGame.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

<br />  
<br />  
[<- Previous](PacManStyleGame_6.html)&nbsp;&nbsp;&nbsp;[Home](../../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](PacManStyleGame_8.html)
<br />  
<br />  
<br />  
<br />  