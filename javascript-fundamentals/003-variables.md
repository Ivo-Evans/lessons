# Variables

So far, in our programs, we've plugged values into console.log, and seen results. But an essential part of programming is tracking change over the course of the execution of a program. That is one fo the things variables are for. Variables are like _names_ we give to values. Once we have given a name to a value at the beginning of our program's execution, we can use the name as a fixed point to observe changes.

Variables also provide other benefits, including:
- letting you use a value in multiple places but only define it once. For instance, say you're making a video game and a number of your functions use the speed at which enemies move. You could assign this information to a variable, and then use the variable throughout your program. That way, if you wanted to adjust the settings, you would only need to change the code in one place.
- increasing code clarity by giving names to values. This can be useful even if they never change and you only use them once

## Syntax

In JavaScript, when you use a variable, you declare it by preceding the variable name with the keyword let, const or var:

```
let myVar = 5
const myOtherVar = 10
var thisAintMyVar = "fourteen"
```

These three kinds of variable are different, but don't worry too much about it for now, and use let as standard. var is from an older version of JavaScript (ES5, superseded in 2015) and no-one really uses it any more, because it's a bit rubbish (there'll be a lesson later, on scope, where we go into the difference between let and var). We'll touch on _const_ in the next section.

You can, actually, use a variable without declaring it, but this is a big no-no - it will cause you problems later on down the line.

Once you have declared a variable, you cannot declare it again (unless you are in a different _scope_ - a topic for another day)

By convention, JavaScript identifiers use camelCase - the first word is lower case, and every next word starts with an uppercase character. There are no underscores or dashes, and starting with a number and most symbols is actually illegal - it will break your code.


## Note this: the assignment operator is not the equality operator

A really standard confusion for beginners is between = and ==. == is the equality operator and it tests a logical relationship, returning either true or false. = is the assignment operator, and it creates a relationship between a value and a name. Its return value is almost always irrelevant. Back in the day, I found it helpful to think that = _creates_ reality, and == _describes_ it.

## Challenge

 We're working up to an actual puzzle challenge, but first, you need to know syntax. So the challenge today is to continue to familiarise yourself with the command line, this time by making changes to the filesystem. The instructions are in the third entry in the command-line appendix.


