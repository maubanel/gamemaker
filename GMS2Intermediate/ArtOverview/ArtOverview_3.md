---
layout: default
title:  "Art Overview III"
---

<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Create a new 64 x 64 image with a white background.  Select a light green color:  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LightGreenGrassColor.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Use the **Paint Bucket Tool** and fill in the whole sprite with that green color:  
</div>
</div>
<div class="col-12 col-lg-8">  
<img src="images/Paintbucket.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Select **Filter -> Noise -> Add Noise** to bring up the **Add Noise** menu:      
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddNoise.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Set **Amount** to `3` (or something close to this).  We will keep **Distribution** at **Gaussian** and **Monochromatic** checked as we want it to all stay green:      
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/3Noise.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Now your tile should look something like:  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Grass.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Select **Filter -> Other -> Offset** to bring up the **Offset** menu and play with the vertical and horizontal shift.  In my case I don't see a line so I don't have anything to clean up on the inside of the sprite.  Remember to ensure that this tiles correctly we should not touch any of the pixels along the edge:  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GrassOffset.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. We **Select All** and **Copy Merged** then move back to our Tilesheet.  We paste our newly made grass texture there. Use your **Move Tool** to position it in a grid area like:  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GridGrass.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. This is very important so that the tile lines up on a 64 x 64 pixel boundary.  Otherwise it will not be placed correctly in the room in GameMaker.  It is always critical that you leave the top left tile empty as this is a new requirement of [GameMaker Studio 2](https://docs2.yoyogames.com/source/_build/2_interface/1_editors/tilesets.html).  Always name your layers in photoshop to keep them neat, so name this **Regular Grass**:  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RegularGrass.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Before We can bring in the tile layer we created in GameMaker we need to export it.  Export the file as a PNG to the desktop (or any folder you want) and call it `BkgSpriteSheet`.  Your PNG should look like:  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ExportTile1.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>
<div class="row">
<div class="col">
<img src="images/ExportTile2.jpg" class="img-fluid" alt="Create new object with button">
</div>
<div class="col">
<img src="images/ExportTile3.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Not too interesting but lets see how we integrate it with GameMaker.  Lets go back to the GameMaker project and right click on Tileset and call it `TlsBkg`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateNewTileset.jpg" class="img-fluid" alt="Create new object with button"> 
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  We also need to import the tileset as a sprite before we can use it.  Create a new **Sprite** and press **Import** and select the file you just exported from Photoshop.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BkgSpriteSheet.jpg" class="img-fluid" alt="Create new object with button"> 
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Call it `SprBkgSprite`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SprBkgSprite.jpg" class="img-fluid" alt="Create new object with button"> 
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Double click on `TlsBkg` and assign the newly imported sprite. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectBkgSpriteInSheet.jpg" class="img-fluid" alt="Create new object with button"> 
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Change **_Tile Width_** and **_Tile Height_** to `64` by `64`:    
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/64x64SpriteSheet.jpg" class="img-fluid" alt="Create new object with button"> 
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Now create a new **Room** and move it to the top and call it `LvlTest3`.  Move it to the top of the room list.  Add a new **Tile Layer** and call it `MainTiles`:  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TileSetLayer.jpg" class="img-fluid" alt="Create new object with button"> 
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Select the one tile you created and paint it over the room layer by left clicking in room.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PaintTilesInRoom.jpg" class="img-fluid" alt="Create new object with button"> 
</div>
</div>

___ 

<br><br>
[<- Previous](ArtOverview_2.html)&nbsp;&nbsp;&nbsp;[Home](../../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](ArtOverview_4.html)
<br />  
<br />  
<br />  
<br />  