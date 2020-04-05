# Hello, world – strings, functions, objects and data types.

In this lesson you’re going to go through a right of passage for anyone learning a programming language: you're going to write a 'hello world' program, a program that prints the text 'hello, world' to the screen. The JavaScript hello world program gives us a good opportunity to learn about how to run JavaScript code, and some fundamental building blocks of the JavaScript language. Since this is your first lesson, I won't start you out with a puzzle. I'll just tell you how to write the hello world program. The program looks like this:

```javascript
console.log("hello, world");
```

## Running a JavaScript program

But how are we to run it? What are you supposed to do with this program? JavaScript is a wonderfully pervasive language, and so I can think of at least five ways to do so, ordered in terms of ease:

- you could go to https://repl.it/languages/javascript, enter it on the left, and see it on the right
- you could open your browser's console and enter it there
- you could put it in a website, and then run the website
- you could download node.js on the command line, and then run it in the node command-line repl
- you could download node.js on the command line, write a .js file, and then execute that file on the command line with node.

We'll get on to all of these, but as we start, let's just use repl.it which provides a useful sandbox for testing out JavaScript, but which won't work for more complex projects. If you haven't already, go to it now and test out the application.

I strongly recommend actually writing this out, instead of copy and pasting it (and I'm not alone there). Actually enacting something, piece by piece, is essential for learning.

## Our hello world program

How exactly does the program work? There's actually quite a lot going on:

1. the word console
2. the full stop
3. the word log
4. the brackets that come after log
5. the expression inside the brackets

Let's start at the end of our list, and work back. I think that, as you go through this section, it might be a good idea to keep a list of new words written on paper, and then you can go through defining them afterwards. If you can get a handle on the concepts and vocabulary introduced here, you'll be off to a running start. On the other hand, don't get _too_ stressed out: this is real brick-and-mortar stuff, so you'll encounter all of it again.

### data-types: a first pass

The statement inside the brackets is what's known as a 'string'. It's the basic way that computers represent text which is supposed to be read as text. For instance, if you write

```javascript
console.log("5 + 5");
```

you'll get a very different result to if you type

```javascript
console.log(5 + 5);
```

(the semi-colons in this example are inconsequential)

'string' is one data type, or type of value, and number is another. There are more (in the region of 7, although this number is disputable) and they all fall into one of two categories.

It's not uncommon for the content of strings to be evaluated, and for that to have some impact on the execution of later code. I found this conclusion kind of problematic at first, because strings are supposed to be read as text. But actually it makes perfect sence: programs can 'talk to each other', and to themselves, and when they do they have to use _some_ kind of value.

You encode strings by surrounding the text in either ', " or ` (a backtick).

### functions

So we've learnt a little bit about data types. Now what about these brackets? The brackets are intimately connected to their preceding word, log. log is a 'function', and when you place brackets after a function's name, you 'call' the function. functions, along with operators, are how you turn inert data into a program that changes the state of values, and to 'call' a function is simply to use it.

Functions are actually little programs themselves, which we can reuse in our code, passing them different 'arguments' to change the details of what they do. For instance, console.log will always log its argument to the console. When that argument is 'hello, world', it logs 'hello, world' to the console. Programmers define their own functions all the time, and we'll do so too pretty soon, but not today.

### objects

If putting brackets after a function lets you call it, you might think that you could write our program as:

```javascript
log("hello world");
```

However, if you do that, you'll get an error, something like

```
  ReferenceError: log is not defined
```

It's a good idea to try to read error messages, even when they're overwhelming. They are actually writtent to help you.

So why does the JavaScript engine think log is not defined, when we ran it above?

It is because the log we used was _stored_ in an 'object'. An object is a data structure that lets you associate values with names, or 'keys' (like the key in a cipher, which lets you access otherwise hidden information). _log_ is a key, which is associated with a function, a function we all know and love, which takes an argument and prints it to the console. This function is 'inside' the object `console`, and we can't use the function unless we take it out of `console`. One way to do that is with the dot notation. Another is with square brackets, which are on balance a bit better, but which we'll learn about later.

The word console in our program is not the actual console, it is just an _object_ that JavaScript gives us so that we can indicate that we want to do something to the actual console.

So the dot in our program gets the function `log` out of the object console, and let's us _call_ the function by putting brackets after the function's name.

### data-types: second pass

I said above that strings and numbers are two kinds of value, or two data types.

Well, object is also a data type. Clearly, however, it is a different _kind_ of data-type. strings and numbers are simple 'primitive' values. Objects, on the other hand, seem more like containers (in fact they're more like telephone books, which provide addresses for values, but you don't need to know that now).

Although there are many kinds of value, they fall into two categories: primitive types and reference types. Primitive types are simple kinds of data, and reference types can contain multiple values.

As it so turns out, functions are reference types too, although they're typically not talked about as such. At this point it might seem like everything - every part of every line of code - is a value! In JavaScript, this isn't so far from the truth, but there are a few things we'll cover next time that aren't values:

- operators
- identifiers (basically, names for things)

We've actually already covered operators. The dot is an operator for getting the properties of objects, and brackets, called directly after an identifier like log, are the function invocation operator (but no one actually says this).

### A challenge

You just covered **a lot** of information. I'd like you to investigate a bit by noodling around in your code editor.

You can actually put the function we just wrote inside another console log!

```javascript
console.log(console.log("hello, world"));
```

Try systematically removing parts and seeing what gets printed to the terminal. Errors are ok: they tell you the rules.
