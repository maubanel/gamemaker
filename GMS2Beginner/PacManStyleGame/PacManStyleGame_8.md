---
layout: default
title:  "Moving 3 Ways Part I"
---

_____ 

### Timer

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We need a timer to keep track of the two modes the ghost changes between.  Open `oGameManager` and add a variable to keep track of time in seconds:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChaseTimeVariableAdded.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Step Event** to the game manager and increment the timer:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChaseTimerInStepUpdated.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

### Chase and Scatter

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. The ghost switches between 3 modes.  Lets focus on the scatter and chase.  Lets keep track of which mode they are in with an enumerator in `oGameManager` **Create Event**.  We will also keep a game state Mode as some ghosts will be in frightened mode and some coming of the hotel will be back in the main state:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ModeEnumManager.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Initialize all of these variables in Blinky's create event:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BlinkyScatterCreate.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Update chase target in step event if ghost is in chase mode:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChaseInStepGhost.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change from hardcoded values to the chase variables:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/UnhardCodeTargets.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>



_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add variables for the time lengths for the four phases.  The final phase of chase is unlimited so we don't have a start time for it.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BlinkyChaseScatterVars.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create a new script called `ModeTimer` and make the first change:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ModeTimerFirstSwitch.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call the script from `oGameManager` **Step Event**.  Play the game and when Blinky reaches to top right he should go to chase the player:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ModeTimerFunctionCall.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now you need to monitor for GameManager mode changes in Blinky.  Edit its step event and add:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BlinkyMonitorGMStatE.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add the next transition back to the Scatter mode.  We also need to reset the target and we only need to do this once so we should do it in this script:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Chase1ToScatter2.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. In Blinky's step script add the watcher when he is in CHASE mode:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BlinkyMonitorGMStateB.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Next two transitions:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Scatter2ToScatter3.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Next two transitions:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Scatter2ToScatter3.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Finish it up:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RestOfScatterToChase.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


_____ 

### Ghost Killing Player
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. When the player occupies the same square as a ghost the player dies.  The game pauses, the ghosts disappear, the dots stay the same, the player animates a quick death then the game starts again with the ghosts back in their initial state. Lets add the death animation.  Right click on Sprite and import a new image and import the `sPacManDeath_strip11` animation.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ImportPacDeath.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call the sprite `sPacManDeath` and change the frame-rate to 10 FPS.  Play back the animation and adjust the speed to your liking.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacDeathSpriteFramerate.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets add `PLAYERDEAD` go `GhostMode` enumerator:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PlayerDeadToGhostMode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a new **Script** called `CheckForPlayerKill` and add a check to see if they inhabit the same square:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PlayerKillScript.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call the script at the top of `oBlinky` **StepEvent**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CheckForPlayerKillCalledFromGhost.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. When you die we want the player to stop.  So lets wrap all the logic in an if statement:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FreezePlayerOnDeath.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. At the very bottom of the if we stop the player:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StopPlayerCold.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Test it and notice tha the timer is still switching modes so we leave death mode.  Lets change this.  Go to the GameManager step script and reset the clock when player dies.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/KillClockOnDeath.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets freeze the ghosts. Wrap Blinkys movements in an if:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/WrapBlinkyDead.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Freeze speed at end:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FreezeBSpeedWhenPDead.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Stop checking for player kill if already diead:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DontKillWhenPDead.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Trigger an alarm when player dies to play animation and make ghosts disappear:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CheckForPlayerKill.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create a new **Scripts** and call it `CheckForPlayerKill`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CheckForPlayerKill.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. To makes all ghosts disappear create ghost parent:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateGhostParent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Set Blinky's parent to ghost parent:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetToGhostParent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Alarm0** event to Blinky and add:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Alarm0BlinkyKillPAnim.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create a PacManPreGame script to pause 2 seconds before starting game:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacManPreScript.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Trigger the script:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PacManStepTriggerGameStartInFut.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a Alarm0 to pac man and add:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Alam0PacMan.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a script called Reset Ghosts
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ResetGhostsScript.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 


[<- Previous](PacManStyleGame_7.html)&nbsp;&nbsp;&nbsp;[Home](../../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](PacManStyleGame_9.html)
<br />  
<br />  
<br />  
<br />  