---
layout: default
title:  "Naming Conventions"
---

# Class Naming Convention 

* All new variables introduced should have a comment explaining its function unless immediately obvious (be careful).  For example:  

```c
//Add to Player score global variable
global.pScore += 10;
```
* All variable names start with lower case letter
and [camel case](https://en.wikipedia.org/wiki/CamelCase) (no underline). For example,
```playerSpeed```.

* All assets are to be written in [camel case](https://en.wikipedia.org/wiki/CamelCase) and start with a capital letter.  Use a 3 letter abbreviation for their asset type:
	
	1. Sprites: Spr
	2. TileSets: Til
	3. Sounds: Snd
	4. Paths: Pat
	5. Scripts: Scr
	6. Fonts: Fnt
	7. Timelines: Tml
	8. Objects: Obj
	9. Rooms: Lvl


For example:

```c
SprPlayer
ObjEnemy
ScrObjectCreate
LvlOne
```

* All scripts that are not directly attached to the event type in the editor are to be written in [camel case](https://en.wikipedia.org/wiki/CamelCase).  They should all start with asset type **Scr**, include the name (for example **Player**) then end with the event type they are bound to.  For example:  

```c
ScrPlayerMovementStep
```

* All code should be properly indented to reflect scope (nested loops should be tabbed).  All brackets should start and end on their own line.  For example:  

```c
repeat(10)
{
	repeat(5)
	{
		//...do something 5 times
	}

	//...do something 10 times
}
```

* All loops should be enclosed in parenthesis.  For example:  

```c
if (y > 10)
{
	//..do something
}
```

* All lines should terminate with a semicolon ( **;** ). For
example, ```playerSpeed = 5;```

* All boolean variables should be in the form of a question.  For example:

```c
canShoot = true;
```


<br />
[Home](../../index.html)

<br />
<br />
<br />
<br />