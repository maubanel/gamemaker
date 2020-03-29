---
layout: default
title:  "Variables"
---

# Variables

A [variable](https://en.wikipedia.org/wiki/Variable_(computer_science)) in Gamemaker (or any other programming language) is a storage location (container) for a value.  This value can either be a numerical value, or a series of characters (words) referred to a a [string](https://en.wikipedia.org/wiki/String_(computer_science)).

Variables in GameMaker do not have declared types.  We can enter two types; a [real number](http://docs.yoyogames.com/source/dadiospice/002_reference/maths/real%20valued%20functions/) (any number either whole or decimal) or a string (a series of characters). The computer reads anything within two `"..."` as a [string](https://en.wikipedia.org/wiki/String_(computer_science)) and a number on its own as a [real number](http://docs.yoyogames.com/source/dadiospice/002_reference/maths/real%20valued%20functions/). For example:
```c
x = 10;
name = "Marc";
```

The variable tells the computer to reserve memory and is referenced by the identifier we created called ``` x ``` and puts the numeric value ``` 10 ``` into it.  Therefore everywhere you use the variable identifier ``` x ```, the computer will use ``` 10 ```.  

If the value is contained within `" "`, then it will not have a numeric value but will be considered a string; a series of letters.  If the computer sees the variable identifier ``` name ```, the computer will use ``` Marc ``` in the above example (it ignores the quotation marks).  The single equal sign assigns the value to the variable name.  You can only have a single variable identifier on the left hand side of the _equal sign_, but can assign a value that is made up of multiple operations. For example:  
```c
x = 10 + 5;
name = "Marc" + "is here.";
```
In the above example ``` x ``` is now equal to `15` and  ``` name ``` is now equal to `Marc is here.` With numeric values the operators perform arithmetic and with strings it concatonates the strings together.  


> In GML a variable has a name that must start with a letter and can contain only letters, numbers, and the underscore symbol '_' with a maximum length of 64 symbols (no spaces allowed). So, valid variables are identifiers like `fish`, `foo_bar`, `num1`, and invalid variables would be <s>'6fish'</s>, <s>foo bar</s>, or <s>*num</s>. - GameMaker Manual