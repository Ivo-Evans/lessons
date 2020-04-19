# Recursion

A __recursive function__ is a function that calls itself, and it's what we'll be focussing on here. 


## A simple example of recursion

Let's imagine we already have two functions. The first, getResponse(), prompts a user for a response and returns that response. (Let's furthermore asume that getResponse() is 'blocking' - while we wait for the user to enter their answer, the whole program pauses.) The second, validateAnswer(), makes sure that the answer is either 'yes' or 'no', and returns ```true``` or ```false```. Our aim is to ensure that the user enters yes or no, not something else. If they answer something else, like 'pineapples', we should simply ask them again. One way to achieve this effect would be with recursion:

```javascript
function askQuestion(questionText) {
  let answer = getResponse(questionText)
  if (validateAnswer(answer)) {
    return /* Return the next thing you want to do in your program, like ask another question, or process the information you received */
  } else {
    return askQuestion(questionText)
  }
}
```

One new thing here is the if () {} else {} block. We'll cover logic in a later lesson, but I think you can understand what they're doing here.

The way that askQuestion works is this:
  - it uses helper functions to ask a question and validate an answer
  - if the amswer is valid, it moves on
  - if the answer is not valid, it calls itself


## The base-case
The inclusion of some logic in askQuestion wasn't coincidental. When recursing, you need some branching possibilities in your code, so that you can say, _if_ this happens, recurse, _otherwise_ stop recursing. The condition on which the function stops recursing is called the __base-case__, and forgetting or messing-up base-cases is a common pitfall. When you write a recursive function that doesn't have a base-case, you'll get an error like 'stack trace too deep'. This means that the JavaScript program has recursed so many times that the compiler (or whoever wrote the compiler) no longer believes that your code is working like it is supposed to. 


## Tangent: How recursion works: the call stack
This is a good opportunity to explain the concept of the call-stack. When I first learnt about recursion, I wasted a lot of time speculating about how it actually worked under the hood (for instance, what gets resolved first, the deepest or the shallowest function call, and how are jobs scheduled), so I thought I'd just tell you how it actually does work. 

A stack is a computer science data structure. Like an array (an ordered list), it is disarmingly simple: we just need a name for it. It is a last-in-first-out data structure, meaning that, if you put something on top of the stack, you can only get it off the top again, never from the middle or the bottom. Think of it like a stack of heavy plates: naturally, you want to take plates off the top, and add them to the top, and nowhere else. Anything else contravenes the logic of the stack.

When JavaScript executes code, it uses a stack, called the call-stack, to prioritise tasks. It goes from the first to the last line of code, executing tasks by adding and then removing them from the call-stack. When it sees an expression that it has to _resolve_, it adds that expression to the stack, and once the expression has been resolved, it removes the expression from the stack. A function call is an expression that needs to be resolved. When JavaScript tries to resolve a function call, it goes to the beginning of the function definition, and starts from there, going from the first line to the last line of the function definition. Extra expressions inside the function that need to be resolved are added to the stack. 

I've written an animated example which you can find [here](http://latentflip.com/loupe/?code=ZnVuY3Rpb24gZG91YmxlKG4pIHsKICAgIGxldCBxdWFydGVyID0gbiAvIDQKICAgIHJldHVybiBxdWFydGVyICogODsKfQoKY29uc29sZS5sb2coZG91YmxlKDIpKQoKY29uc29sZS5sb2coNSs1KQ%3D%3D!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D). The website is a bit buggy, but the talk is excellent - I was going to link you to it later in the course.

## Getting back to base-cases

### Kinds of base-case: external mutation with irrelevant return
Recursion is probably easiest to understand when you use it in an impure way. Using it this way is atypical and, probably, inadvisable. Let's take a look at an example anyway


```javascript
const array = []
function generateRange(n) {
  if (array.length === n) {
    return
  } else {
    array.push(array.length + 1)
    generateRange(n)
  }
}
```

As mentioned, this is bad code. Firstly, it mutates (and depends on) an external variable, array. Secondly, there are cleaner, more versatile ways to do this. Nevertheless, I think it provides a good example of a kind of recursion - where the base-case is external, and the function's return value is not the most important thing. 

### Kinds of base-case: passing parameters and return down the call-stack
Normally a recursive function looks more like this - you'll recognise it as a recursive version of the rotate() function I wrote last time:

```javascript
function rotate(array, times) {
  array = [ ... array]
  if (times === 0) {
    return array
  } else {
    array.push(array.shift())
    return rotate(array, times - 1)
  }
}
```

On each new level of recursion, the function tries to _return_ the product of calling itself with one key difference - a partially rotated array, and an index reduced by one - until finally it is passed 0 as a parameter, and then it succesfully returns, not itself, but the array. This array is then passed down each function in the chain, like a holy grail, until the outermost function passes it on. 

This pattern of nested returning, with different parameters, is more common for recursion.

## Recursion versus iteration
So, we've seen that recursion and iteration can often do the same job. 

Which one should we use? In the functions we've seen above, iteration certainly takes less lines to write. It also takes less brain power to process, and less _computer power_ to process. Thus, for a lot of general applications, iteration wins the day. 

Recursion arguably wins the aesthetic debate. When I first wrote a rotate() function, I went straight for a recursive version because I loved the corkscrewing logic. Recursion is also a better fit with a lot of mathematics, and a lot of the classic algorithms in computer science are recursive. These algorithms are possibly optimal for their jobs, and in these cases, recursion is appropriate. 

There's also a really nice example of a recursive function in [this book](https://eloquentjavascript.net/03_functions.html) - scroll down near the end of the chapter to find the section on recursion. Don't worry if you don't understand it - I didn't either, when I read it months ago - but it is worth trying. Because I studied it then, when I came back to check it out this time, I could understand it relatively easily - graft causes progress.  

## Challenge
The challenge today is to write a factorialising program that uses recursion, instead of looping. Good luck!