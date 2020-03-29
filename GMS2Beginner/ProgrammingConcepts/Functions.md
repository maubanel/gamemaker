---
layout: default
title:  "Functions"
---

# Functions
A function performs a task in the program.  A function can be found by looking for a name followed by ( ) parenthesis (round brackets).

```c
function (parameters);
```  

A function can be passed data that are called parameters.  It can also be passed multiple parameters separated by commas.

 ```c
function (parameter1, parameter2, parameter3);
```  

A function can be returned data so you can assign the output of the function to a variable.  

```c
average = AverageFunction (1, 2, 3);
//AverageFunction returns the value 2 which is the average of the above 3 numbers
```  

GameMaker functions are written in lower case with _ between words.  An example would be:  

```c
keyboard_check(key);
//keyboard_check is a built in function.
```  

It is suggested that we use capital camel case to differentiate between functions we write ( DrawPrint(data) )and GameMaker provided ones (keyboard_check(key) ).
<br />  
<br />  
<br />  
<br />  