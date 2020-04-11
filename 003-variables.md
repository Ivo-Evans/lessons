# Variables

So far, in our programs, we've plugged values into console.log, and seen results. But an essential part of programming is tracking change over the course of the execution of a program. That is where variables come in. Variables are like _names_ we give to values. Once we have given a name to a value at the beginning of our program's execution, we can use the name as a fixed point to observe changes.

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

By convention, JavaScript identifiers use pascalCase - the first word is lower case, and every next word starts with an uppercase character. There are no underscores or dashes. Starting with a number or symbol is actually illegal - it will break your code.

## Word and reference - a philosophical issue

Because variables are like names, people often make a mistake about variables that they also make about words: thinking about the word or variable as if it is the thing it refers to. In fact, however, this isn't right. While it is a tautology that all apples are apples, it is, at least on certain views, not a tautology that every reference of the word 'apple' is an apple - even if we think that statement is definitely true, it isn't a tautology. Anyway, there's a tangent lurking around the corner here. The upshot, for coding, is that the value of a variable can change in two ways:

- the thing the variable points to can change (this is called 'mutation')
- the variable can be made to point to a new thing (this is called reassignment)

Now would be a great time to talk about const variables, or constants. A const variable cannot be reassigned:

```
let a = "a" // fine
a = "b" // fine
const b = "b" // fine
b = "c" // TypeError: invalid assignment to const `b'
```

However, a const variable's reference _can_ change: the thing it points to can mutate. To see how, let's make an array. An array is what's called an _indexed list_. This means that every value in the list can be accessed by its position in the list. Any kind of value can be an array element, and an array acts as a kind of rolodex for its elements. It is, therefore, a reference type. You mark arrays with square brackets:

```
const firstArray = []
```

There are four cardinal functions for arrays, which, I believe, are effectively universal across programming languages: push, pop, shift and unshift. push(x) adds x onto the end of an array, pop() removes the last item from an array, shift() removes the first item from an array, and unshift(x) adds x on to the start of an array. Let's push a value onto our array:

```
firstArray.push(5)
console.log(firstArray);
```

Now, back to the topic at hand. firstArray points to the same array as it did before we pushed 5 on, but the array has mutated. Not all values can be mutated in this way - only reference types. Primitives, in JavaScript, are **immutable**. Here's the list of primitive data-types:

- string
- number
- bigint (really big integers)
- boolean
- undefined
- symbol

None of these values can be mutated. If you assign them to a variable, and then change the value of that variable, the variable is pointing to a different value.

## Arrays are 0-indexed

Since we're talking about arrays, there's something I have to mention. To look up an array element by its place in the list, you can use [n], where n is some number, after the array (or a variable that points to it). But the mindbender is that **the counting starts from 0**, so the first array element is at index 0. Arrays are 0-indexed. The first element is at index 0, the second one at index 1 etc.

```
firstArray[0]
```

## Assignment and reassignment

So, we've talked a bit about mutation. Time to talk about reassignment. I think you will have already figured out by now that, e.g., a let variable can be reassigned:

```
let five = 5
five = "five"
console.log(five)
```

But we can get more creative with reassignment. One thing we can do is use a variable to update itself. The assignment operator is what's called _right-associative_ - it reads the right hand side first. It is also [low-precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence), so you can guarantee that the right hand side will be evaluated before the assignment is performed.

```
let hello = "hell"
hello = hello + "o"
console.log(hello)
```

## Luxury operators

JavaScript has a bunch of reassignment operators to make what we just did quicker. Here they are:

```
++
--
+=
-=
*=
/=
%=
**=
```

These last four are pretty rare, but it's good to know they exist. I'll leave it to you to experiment with these operators to figure out how they work, but I'll give you a clue: the first two are different to the rest, and they have two versions each. The link above could direct you to useful resources.

## The assignment operator is not the equality operator

A really standard confusion for beginners is between = and ==. == is the equality operator and it tests a logical relationship, returning either true or false. = is the assignment operator, and it creates a relationship between a value and a name. Its return value is almost always irrelevant. Back in the day, I found it helpful to think that = _creates_ reality, and == _describes_ it.

## Challenge

Yesterday you explored the command line a bit: today you'll do some more exploring, except that instead of merely navigating, you'll explore its creative and destructive powers, with mkdir, touch, rm.

mkdir makes a directory. Give it a name like this

```
  mkdir my-dir
```

give it multiple names separated by spaces to make an extra directory.

touch creates a file, unless there is already a file of that name in the working directory, and then it does nothing - like the inverse of touching a moth's wing. The file is an empty, plain-text file. It doesn't even need a file extension. All files, at base, are like this: even a JPEG is a long string.

rm is for removing things - but there's a catch. rm will remove single files, or empty folders, but if the folder has anything in it, you'll need to use rm -r, rm 'recursive'. You can also use man rm, or indeed man any other command, to see a manual page for the command.

So, cd around a bit and try out these commands. We're working up to an actual puzzle challenge, but first, you need to know syntax
