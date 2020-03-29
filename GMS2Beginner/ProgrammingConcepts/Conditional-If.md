---
layout: default
title:  "Conditional If Statement"
---

# Conditional If () statement.
An if-statement chooses looks at what is within the parenthesis and decides whether the condition is true or false.  It its condition is true, the first statement is executed.  Otherwise the second statement is.  

```c
if (true)
{
	...run something if if() is true.
}
else
{
	...run something else is if () is false.
}
```  

Within the brackets of an if statement has to resolve to a boolean true, false statement.  So  

```c
if (5 < 3)
{
	...run something if if() is true.
}
else
{
	...run something else is if () is false.
}
//the false else condition will run
``` 

It is more common to use variables:
```c
x = 10;
if (x < 3)
{
	DrawPrint("x is less than 3")
}
else
{
	DrawPrint ("x is greather or equal to 3")
}
``` 

You can use _<_ (less than), _<=_ (less than or equal), _>_ (greater than), _>=_ (greater than or equal), _==_ (the same), _!=_ (different) to name a few.

You are also able to follow up an if with an else if (or as many as you need). For example we could check to see what decade someone was born in would be:

```c
if (age < 6 )
{
	DrawPrint("You were born after 2010");
}
else if (age < 16)
{
	DrawPrint("You were born after 2000");
}
else if (age < 26)
{
	DrawPrint("You were born in the 90's");
}
else
{
	DrawPrint("You are old");
}
```

The first time one of the if statements or else if statements are true then the code between the { } is run and the rest of the condition is ignored.  So if the age is 3 it will succeed with age < 6 then stop performing checks. 


<br />  
<br />  
<br />  
<br />  