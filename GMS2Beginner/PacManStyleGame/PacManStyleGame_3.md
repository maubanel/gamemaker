---
layout: default
title:  "Moving 3 Ways Part I"
---


_____ 

### Track Directions
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets create 4 variables that tracks which direction we are moving in.  We create 4 booleans and default them all to false except left which is true and the default position.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DirectionBooleansPacMan.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

### Move Left and Right
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets add controls so we can move PacMan left and right.  We use the `keyboard_check(key)` function then change the `image_angle` and `direction` of the motion vector.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveLeftAndRight.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

### Collision Detection
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We need to add colision detection so if Pac-Man hits a maze piece it stops.  We will create a spreadsheet where 0 is non-traversable, 1 is a small dot, 2 is a large dot, and 3 is traversable with no dot.  You spreadsheet should look like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpreadsheetMazeCollision.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  You then need to save the file as a csv comma deliniated.  Cut and paste it into GameMaker into the **Create Event** of `oGameManager` and add commas at the end of each line.  Now you can't instantiate an array in a single line so we will have to create a function that will load this into a 2-dimensional array.  Use the function `MakeCollisionArray`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CollisionArrayFunction.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now lets create a new script that converts that single list into a 2 dimensional array that we can use:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeCollisionArrayFunction.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 


<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  We need to now show where the PacMan can move with debug.  So lets add to `oGrid` **Draw** event:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/oGridDrawDebugPath.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Run the game and you should see green squares where PacMan can move:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MazeDebugGreen.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now we need to keep track of whether the character can move into the next square, if not they will need to stop at the very begining of that square. Create a new script to set all directions to false except for the one we are moving in.  We will use the vk_left etc... as constants.  Create a script called `SetDirections` and add:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/IsMoveLeftIsMoveRight.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Call this script from `oPacMan` **Step Event**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetDirectionsLeftAndRight.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now check to see if next left square is free when moving left and if not then place in middle of square.  Add a new script called `IsSpaceFreeToMove` and add:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/IsSpaceFeeToMoveStart.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Call the script from `oPacMan` step:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/IsSpaceFreeToMoveCall.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Run the game and you get stuck when you go to the left.  We need to give speed back to the player when they press the arrow keys to move in a different direction.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacManStuckOnLeft.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Lets add a check to only run the code if the player is changing diretions and add speed to the player when turning.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddRightTurnPacMan.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Test the game left and right.  OK, the player stops on the left, but not on the right.  Lets add the collision for moving right.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CollisionRight.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Lets clean up the code by adding a function for getting center position of grid.  Create a new **Script** called `GetGridCenterWorldPos` and add:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetGridCenterPo.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Lets go back to `IsSpaceFreeToMove` and change:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/IsSpaceFreeRefactored.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now press and hold left then press right and do the opposite.  See how the controls are not consistent?  This is because of our if statement running is a specific order.  Lets not do that, lets check for the last key pressed, so changed the algorithm.  We are going to add last key checked but need to set it to left for the begining of the game.  Lets check for the last key pressed, so changed the algorithm:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RefactorMovingLeftRightLastKey.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now we will have different movement for turning than moving laterally left to right and up to down.  So lets add two more variables to PacMan:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/HorVerBoolPac.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Create a new script called `UpdateHorVerScript` and add:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/UpdateHorVerScript.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now open `oPacMan` **Step Event** and call this at the top:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/UpdateHorVerCall.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Create a new script called `PacManMoveLaterally` and copy and paste the movement cutting it out of the **Step Event**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacManUpdateLaterally.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Call it again from the **Step Event**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacManMoveLaterallyCall.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Play the game and you can now see that it works exaclty the same as previous.  Now lets add going up and down. First lets a horizontal check to `PacManCanMoveLaterally`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CheckThatMOvementIsLateral.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Add the vertical checks for `PacManMoveLaterally`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddVErtical.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Add up and down to `IsSpaceFreeToMove`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddUpDownToIsSpaceFreeToMove.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Edit `ResetPacManToStart` and change it to a square that is vertical and update variables:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacManStartTestUp.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Change the order in PacMan Create:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChangeOrderPacCreaet.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>


<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Change the default direcxtion to up:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Defultup.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Reset back to previous position.  Start by returning the `ResetPacManToStart` back to the original position:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ResetPacStartPos.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Change `oPacMan` **Creaet Event**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChangePacCreate.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Set IsMoveLeft back to true:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ResetIsMoveLeftToTrue.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 



<br />  
<br />  
[<- Previous](PacManStyleGame_2.html)&nbsp;&nbsp;&nbsp;[Home](../../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](PacManStyleGame_4.html)
<br />  
<br />  
<br />  
<br />  