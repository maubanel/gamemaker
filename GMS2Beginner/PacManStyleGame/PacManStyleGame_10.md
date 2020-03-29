---
layout: default
title:  "Moving 3 Ways Part I"
---

_____ 

### Leave Hotel

_____ 
{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we need to deal with the ghosts in Hotel.  We have the eyes coming back but it needs to change back to Blinky and then Blinky needs to leave hotel and go back to the state that the rest of the game is in. Add to the bottom of `oBlinky` **Step Event** a switch when arrived:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/InHotelModeNow.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We need to add a variable to the ghost that tracks if it is in jail or not.  Open the **Create Event** in `oBlinky` and add:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/InHotelCreateFalse.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. In `oBlinky` **Step Event** in an else on InHotel Switch back to ghost, move back to start point go back to regular game mode.

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ElseForBlinkyStep.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

### Pinky
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Copy the `oBlinky` Object.  Change the sprite to Pinky (you will need to import it) and make the following changes to Blinky's Create event:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PinkyCreateChangesA.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. And:. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PinkyCreateChangesB.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
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
<img src="images/PinkyCreateChangesC.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. and change the scatter target to top left: 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PinkyCreateChangesD.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Make changes to Pinky's **Step Event** and change `oBlinky` to `oPinky` in:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PinkyStepChangeFromBlinkyA.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
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
<img src="images/PinkyStepChangeFromBlinkyB.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now comment out the entire hotel portion as we will be having a point system on when the ghost should leave the hotel.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CommentOutElseHotel.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Put Pinky in the center of the hotel:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PinkyInRoom.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We need add dot counters to the ghosts. Pinky's dot limit is always set to zero, causing him to leave home immediately when every level begins. For the first level, Inky has a limit of 30 dots, and Clyde has a limit of 60. This results in Pinky exiting immediately which, in turn, activates Inky's dot counter. His counter must then reach or exceed 30 dots before he can leave the house. Whenever a life is lost, the system disables (but does not reset) the ghosts' individual dot counters and uses a global dot counter instead. This counter is enabled and reset to zero after a life is lost, counting the number of dots eaten from that point forward.

The three ghosts inside the house must wait for this special counter to tell them when to leave. Pinky is released when the counter value is equal to 7 and Inky is released when it equals 17. The only way to deactivate the counter is for Clyde to be inside the house when the counter equals 32; otherwise, it will keep counting dots even after the ghost house is empty.

So lets create a switch in the **Create Event** for Pinky and a LocalDotLimit and GlobalDotLimit and a counter.

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DotCounterVariables.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

________ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add global varaibles and dot counter in `oGameManager`:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GameManagerGlobalDotsVars.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>__ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets edit the step event and add the else back in:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ElseLocalDotsPinkyA.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
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
<img src="images/ElseLocalDotsPinkyB.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pinky does not start in SCATTER mode.  Open `oGameManager` and edit the **Create Event**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PinkyBugFixScatter.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets change Pinky's targeting to match his rules.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PinkyTargetLogic.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets have the counter switch to global when player dies.  Go to `oPacMan` and find out when we kill the player and make this one line addition:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SwitchLocalDotModeToFalse.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the game and die and it crashes.  Now edit Pinky's step script:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CrashWhenDiePinky.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Same thing for Blinky:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CrashWhenDiePinky.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to the `oPacManStart` script and add Pinky bakc into the level:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewPinkyToPlayerStart.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go the alarm on the same object and add the game mode switch:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Alarm0Pinky.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now the ghosts stay in Fright Mode for 6 seconds, then flash quickly 5 times before going back to normal. Lets add four variables to the `oGameManager`:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FrightVariables.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we need to adjust the timer when in FRIGHT so go to `oGameManager` **Step Event**:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StepTimerAddFright.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we need to adjust the timer when in FRIGHT so go to `oGameManager` **Step Event**:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StepTimerAddFright.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Import the flashing sprite which should be called: `sGhostFrightFlash_strip12.png`.  Center the origin and change the framerate to 30 and call the sprite `sGhostFrightFlash`:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpriteFlightFlash.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Import the flashing sprite which should be called: `sGhostFrightFlash_strip12.png`.  Center the origin and change the framerate to 30 and call the sprite `sGhostFrightFlash`:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpriteFlightFlash.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Before we trigger the animation we need to not have it change animation frames.  Open `GhostDirection` and wrap in an if to only run if in CHASE or SCATTER modes:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GhostWrapInIf.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add to the top of `oBlinky`'s step event a change to the flashing:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GhostBackToNormalAfterFlashing.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the game and die.  The game crashes.  Open `CheckForPlayerKill` and add an else if which fixes one problem:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CrashFixA.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Second problem lies in `oGameManager` **Step Event**.  You need to wrap the whole function in and if to check if oGhostParent exists:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CrashFixB.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

<br />  
<br />  
<br />  
[<- Previous](PacManStyleGame_9.html)&nbsp;&nbsp;&nbsp;[Home](../../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](PacManStyleGame_11.html)
<br />  
<br />  
<br />  
<br />  