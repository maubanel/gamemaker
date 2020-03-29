---
layout: default
title:  "Art Overview I"
---

# Sprites & Tiles
___ 
## Introduction  
<div class="col-12">
<div markdown = "1"> 
{% assign num = 1 %}
{:start="{{ num }}"}
{{ num }}. We will be looking at techniques for creating animations for GameMaker video games.  We will look at pixel art, vector art and some common techniques when building characters and levels.
</div>
</div>

___ 
## Pixel Formats
<div class="col-12">
<div markdown = "1"> 
{% assign num = 1 %}
{:start="{{ num }}"}
{{ num }}. With bitmaps we have a series of pixels.  In a 32 x 32 sprite we have: 32 x 32 = 1,024 total pixels.  The pixel is most likely to contain 32 bits of data (8 bit red, 8 bit green, 8 bit blue, and 8 bit alpha).  8 bits is the binary representation of decimal 256.  So we have 256 values for each of the the R, G, B, A channels.  Some art styles can be saved a lower rates such as 16 bits where we have 4 bits per channel or 32 values for R, G, B, A.
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. There are many different **raster** formats that images can be saved in.  I have highlighted a few in Photoshop that are common: psd, gif, jpg, png, tiff, & targa.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ImageTypes.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. They all have different abilities and there are good reasons to use or not use them in a game.  Let's first look at [lossy](https://en.wikipedia.org/wiki/Lossy_compression) versus [lossless](https://en.wikipedia.org/wiki/Lossless_compression) images.  A lossy image is one where the image size is shrunk by algorithms that change (hopefully not noticably) to save space.  Jpeg (.jpg) files is a common compressed file type.  Here is an example of the plane from the WW2 shooter with the least compression on the left and most on the right:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CompressionArtifacting.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class="col-12">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. There is not only a quality tradeoff with compression.  There is a performance one as well.  Even though compression makes the storage size smaller they have to be decompressed so there is a performance hit.  It is important to note that the format will need to be sent to the GPU in its raw decompressed state so ultimately the entire size is required to display the image. Each game will have different demands for either aesthetic or performance reasons.  In most cases png is the default format to use and is recommended by GameMaker.  Lets look at various formats:

	1.  [Jpeg](https://en.wikipedia.org/wiki/JPEG).  It is a good format for complex images like digital photographs.  It is less effective for simpler graphics (images from Illustrator) with well defined lines.  It is important to note that jpegs do not have an alpha channel so you need to pick a unique color for a background to remove it.

	2.  [Portable Network Graphics Ping](https://en.wikipedia.org/wiki/Portable_Network_Graphics) (png) is a compressed and uncompressed lossless format.  It supports both 24 bit RGB and 32 bit RGBA formats.  

	3.  [Graphics Interchange Format](https://en.wikipedia.org/wiki/GIF) (GIF) is commonly used to store animations as it is one of the few formats that supports them.  It only supports only 8-bit RGB color space and does not support alpha channels. This is far less than jpgs or png's 24 bit colors which makes it only suitable to very simple images.  GIF's compression are better for simpler art like line art or Illustrator files. GIF's are also good for storing low-color sprite data to save size.

	4.  PSD.  I make a lot of sprites in Photoshop and save all the layers and original work.  Unfortunately GameMaker does not support PSD so they need to be exported to one of the above formats.
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Let's look at some of this in action.  [Download](TilesAndBackGrounds.zip) these sample files. Decompress the files and put them in a folder next to your working gamemaker directory.  Start a new **GameMaker Project** and make sure you select **GML** and not Drag-and-Drop.  Call the project `BackgroundTiles`. Lets make a background to look at the same image in different formats. I created a background for you but it is a simple idea.  I have a one pixel wide by room_height (`768`) pixels high with a gradiant.  I exported it from Photoshop using the **File -> Export -> Quick Export as PNG**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SinglePixelLine.jpg" class="img-fluid" alt="Create new object with button">
<img src="images/SinglePixelLineSavePng.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Create a new **Sprite** and call it `SprStaticBkg` and press the **Import** _button_.  Select the png called **BackStripe**(.png) then press **yes** to ignore the pop-up:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ImportStaticBkg1.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>
<div class="row">
<div class="col">
<img src="images/ImportStaticBkg2.jpg" class="img-fluid" alt="Create new object with button">
</div>
<div class="col">
<img src="images/ImportStaticBkg3.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Double click the room and change the name to `LvlTest1`.  Go to the **Background Layer** on the left hand menu and select `SprStatickBkg` as the **Sprite**.  Now it is very hard to see because it is only one pixel wide:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SingleLineBkg.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Why did I make it 1 pixel wide and not just create a sprite that was the size of the room?  I want to be as efficient with my sprites as possible.  Every video card has maximum texture sizes and we can go through that barrier quickly.  I am creating a gradient background with as little data as possible.  So how do I tile this texture horizontally so it fills the whole background?  Just click on the **Horizontal Tile** in the **Background Properties** _panel_ on the left: 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SingleLineBkgTiledHor.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Voila! The background repeats the one pixel line at infinitum (my level can be infinitely wide).  Ok, lets import a jpeg sprite.  I am using the plane from the **WW2 Shooter** as an example.  Create new **Sprite** and press **Import** and select **PlaneJpg**.  Call the sprite `SprPlaneJpg` and it should look like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PlaneJpgSprite.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Create a **Game Object**, attach the `SprPlaneJpg`, place it in the room (make sure you on the **Instances** layer) and run the game.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ObjPlaneJpg.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>
<div class="row">
<div class="col">
<img src="images/ObjPlaneJpgInRoom.jpg" class="img-fluid" alt="Create new object with button">
</div>
<div class="col">
<img src="images/ObjPlaneJpgInGame.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class="col-12">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Now not only do we have a lossy image format but it does not save the Alpha.  What can we do?
</div>
</div>
___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. I can go and **Edit** the image and select the **Color remove** _tool_.  But the edges are anti-aliased which now go to the background white:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/UglyBkgRemoval.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. If you have to use jpegs (I advise you don't, unless you have a good reason to), then make sure your pixels are hard and have no anti aliasing on the outer edges.  Create a solid color.  I also picked a color I am not using in the art to make sure that I get rid of it entirely when I touch it up in GameMaker.  I have done this with a file called **PlaneJpgFixed**.  The only other problem is that the jpeg compression will change the pink so that it can't be eliminated in one step.  Double click `SprPlaneJpg` and re-import the new **PlaneJpgFixed**.  It should look like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpriteJpgFixed.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Now click on **Edit Image** and select the **Color remove** _tool_ and click on the pink:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RemoveBackground.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Now it should look like:  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RemoveBackground2.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. The compression added some noise to the pink so you will have to zoom in and click carefully on the remaining pink pixels.  This took me a while to do but should end up free of all pink pixels and no degradation to the rest of the image:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RemoveBackground3.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>
<div class="row">
<div class="col">
<img src="images/RemoveBackground4.jpg" class="img-fluid" alt="Create new object with button">
</div>
<div class="col">
<img src="images/RemoveBackground5.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Now it looks better in the room and in the game, but we did sacrifice our nice antialiased edge that we would have kept in a PNG format:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/JpgPlaneCleanInRoom.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>
<div class="row">
<div class="col">
<img src="images/JpgPlaneCleanInGame.jpg" class="img-fluid" alt="Create new object with button">
</div>
<div class="col">
<img src="images/ImageTypes.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. Double click on `SprPlaneJpg` and press **Import** and select the **SprPlaneGif** file.  Rename the **Sprite** to be `SprPlaneGif`.  It should look like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PlaneGif.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}.  That looks normal and hey there is an alpha!  With a GIF you can have one pixel be an alpha but there are no gradients, that pixel is either an alpha or it isn't (can't have 50%).  In photoshop it is as simple as clicking a box on the export:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PhotoshopGifSettings.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>

___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. You will see the reduced pallette if you zoom into the plane:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ReducedGifPalette.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>
  
___ 
<div class = "row">
<div class="col-12 col-lg-4 align-self-center">
<div markdown = "1"> 
{% assign num = num | plus: 1 %}
{:start="{{ num }}"}
{{ num }}. I don't recommend using GIFs but many animations come in this format and it is the only raster format that supports animation. Import **PlaneTif** and **PlanePng** and look at them in game.  They save the alpha as well as the nice anti-aliasing and have no artifacting:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PlanTifInGame.jpg" class="img-fluid" alt="Create new object with button">
</div>
</div>


___ 

<br><br>

[Home](../../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](ArtOverview_2.html)
<br />  
<br />  
<br />  