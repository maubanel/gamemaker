---
layout: default
title:  "Moving 3 Ways Part I"
---


_____ 

## Part 3 - Background Tiles

_____ 

### Drawing Tiles
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets right click on **Sprite** and create a new one called `sBackground `.  Click on the size icon and set it to `64` wide by `32` high and make sure the Maintin Aspect Ratio is **unchecked**.  Press Apply.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/sBackgroundSpriteCreate.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Select the second brush size. Select a light blue color. Select the line tool.  Go to `32` on the `x` and start to draw a straight line across the top.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StartDrawingLine.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Tilesets require a single sprite that is blank.  So we leave a 32 by 32 blank piece.  Select the second brush size. Select a light blue color. Select the line tool.  Go to `32` on the `x` and  `1` on the `y` start to draw a straight line across the top.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StartDrawingLine.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Start drawing second line before the halfway point so that Pac-Man can fit.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StartDrawingSecondLine.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Finish drawing second line before the halfway point so that Pac-Man can fit.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinishDrawingSecondLine.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Right click **Tile Set** to create a new tile set.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateTileSet.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Call **Tileset** `tBackground` and select the **Sprite** you just created.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/tBackgroundTilesetCreate.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Click **Tile Set Properties** button:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TileSetProperties.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Set properties to `32` by `32` for width and height.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/32by32Tiles.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Set properties to `32` by `32` for width and height.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/32by32Tiles.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Select the Tile Brush.  This is where we will place these pieces and rotate them without wasting more game space.  Press the shape on the left and place it on the right hand side.  Leave a blank tile between brushes so that it only picks up one at a time in the room.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BushBuilderStraightLineA.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Do this for all four angles and finish the brush.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BushBuilderStraightLineB.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Go into the room and place th elines along the fourth row on the top:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DrawTopLine.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Test it in game and make sure it works!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TopLineInGame.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Draw 8 vertical corner rows on each side.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/VerticalTopLines.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Test it in game and make sure it lines up:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/VerticalTopLinesInGame.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Draw the tunnel portion.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CornersHalfDone.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>

_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Test it in game:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CornersHalfDoneInGame.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Finish the rest of the edges.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CornersDone.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Test it in game.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CornersDoneInGame.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Click the sprite and add some more tiles.  Make it `96` x `32`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/96WideBackgroundSprite.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Draw the corner turn in the Sprite.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DoubleCurve.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Add it to the brush with all 4 rotations.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewBrushWithDoubleCurve.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Place in the room to fill in edges.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinishRoomOutsideCurves.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Add another `32` pixels to sprite.  Make a near turn with pixel in corner.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SingleLineDotInCorner.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Use the circle tool to complete the turn.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SingleLineDotInCornerB.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Add four rotations to brush.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BrushSingleLineDotInCorner.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Fill them in room to complete the corners.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinishOutsideCurves.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Make **Sprite** `128` wide to add more artwork.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Add32PixelsToSprite.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Make straight line at 12 pixels.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StraightLineSprite.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Add to brush in 4 angles.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StraightLineBrush.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Draw the first row of lines in room.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StraightLineRoom.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Test in game:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StraightLineGame.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Make **Sprite** width `256` pixels wide to add the final tiles.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinalSpriteSize.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Add 6 last remaining shapes to the **Sprite** sheet.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinalSprite.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Make all of the brushes with 4 directions except for pink door.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinalBrush.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  This is the final room layout.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinalRoom.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  This is the final layout in game.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinalGame.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  We no longer need the debug so we can comment it out.  Go to `oGrid` and comment out the code in the draw script.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CommentOutGrid.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Go to `oPacMan` draw event and comment out the square but keep the `draw_self()`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CommentOutPacSquare.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 

<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  Play the game and move around the maze, this should be the final layout.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinalGameNoDebug.jpg" class= "img-fluid"  alt="Create new sprite with menu">
</div>
</div>
_____ 


<br />  
<br />  
[<- Previous](PacManStyleGame_4.html)&nbsp;&nbsp;&nbsp;[Home](../../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](PacManStyleGame_6.html)
<br />  
<br />  
<br />  
<br />  