

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Lets fix the first issue.  Lets check before moving that there is a valid space to move into.  Lets add a function called `CanMove`.

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CanMoveDefinition.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Lets call it when moving up:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddCanMoveUp.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now this doesn't fix the not moving up when missing the center.  But it works sometimes and always at the corners.  Lets add collision checks for moving up:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddCanMoveUp.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now Lets add the checks to right:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddCanMoveRight.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Now Lets add the checks to left:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddCanMoveLeft.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Before we finish up lets add controls for going down:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddDownDirection.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Add down as false to all other directions:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddMoveDownCheck.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Add collision detection for moving down:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CollisionDownPacMan.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  One small problem, the game remembers the last key but when it is lifted it records it.  We want to negate the turn.  Add to all four direcitons an extra check that you are still pressing the key:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/andkeyboardCheckFix.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

_____ 
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Go back to **Step Event** and wrap all the movement in an if statement.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/IsTurningFalseCheckf.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>