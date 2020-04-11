# Functions

Functions are reusable sections of code. They go by many names, including method (commonly), and (more rarely) message, subroutine, subprogram and command.

JavaScript has some inbuilt functions, like console.log, and we can define our own.

There's a lot to explain in this lesson, so let's get started.

## Calling functions

We've called two functions so far, console.log and push.

Both times, we followed the function name with brackets. This is essential for calling the function - without brackets, you are passing around the function as a value, rather than using it. Try console logging both these functions. You will encounter an error for push. The error isn't related to the absence of brackets - try to solve it by thinking about how we used push last time.

## Defining your own functions

There are two different approaches to defining your own function. The first is a function _declaration_. It looks like this

### function declarations

```javascript
function squareMe(parameter) {
  console.log(parameter ** 2);
}
```

You then pass the function an _argument_.

```javascript
myOwnFunction(5);
// logs '25'
```

The difference between an argument and a parameter is that an argument is the value we pass into the function, and a parameter is the name we use inside the function to represent the argument. We could use any name we wanted for the parameter - it's a placeholder for the argument that we're going to pass into it.

The distinctive thing about function declarations is that they give their functions names. These names aren't variables, but they are identifiers, so they're in the same broad family as variables.

### function expressions

The other way of creating a function creates an _anonymous_ function. An anonymous function has no inbuilt identifier, although it can still be assigned to a variable, and if it is, it can be called like a declared function. To create an anonymous function, use a function expression:

```javascript
function(parameter) {
  console.log(parameter ** 2)
}
```

How do you think you'd call this function? Take a second to think about it.

There's actually a fair few ways, but I only mentioned one so far, assigning it to a variable:

```javascript
const squareMe = function (number) {
  console.log(number ** 2);
};
squareMe(10);
```

When you assign a function expression to a variable, you're basically writing a function declaration another way. So let's look at a situation where function expressions come into their own.

### callbacks

As mentioned in lesson 1, JavaScript can run in different environments, and one of those is in your browser. JavaScript is the only language that can do this, and this is actually what it was created for: as a language to bring interactivity to the web.

One way it does this is by listening to 'events' on the webpage, like clicking. We're going to add an 'event listener', and then explain the syntax.

```javascript
document.body.addEventListener("keydown", function (event) {
  event.preventDefault();
});
```

#### using the function

What this function does is listen to a keydown event, and prevent the default behaviour. Let's test it out by going to a website (go to a long one, not like Google) and opening our browser console. In Chrome, this is ^-shift-j, and in firefox it is ^-shift-k. You can also right click on something, press inspect, and then find the 'console' tab - the developer tools can be pretty overwhelming, but stick with it!

In the console, you're likely to have a lot of junk showing up. Wait until the junk has slowed down. Then press the ban sign (Chrome), or the bin sign (Firefox), or alternately accept having junk on your screen. Right - we're finally ready to input our function. Click just to the right of the blue arrow in console, copy and paste our function in, and press enter.

(generally typing is better than copy and pasting but the console can be a bit annoying to type in.)

Now, if you close the console, keyboard navigation will not work like it normally does. Space won't jumo the page down, and the arrow keys won't let you navigate. Cool.

What you've done is change the website that the server sent to your computer - you _haven't_ changed the website on the server-side.

#### the function syntax

You might remember the dot syntax from the first lesson, hello world - it gets properties out of objects. the function addEventListener is, in this case, in the body object, and the body object is in the document object - the 'body' here is a JavaScript representation of the html body tag.

We give addEventListener two arguments. The first is a string, representing which kind of event we want to listen for. The second is a function, which we want the browser to call whenever the event happens. Since no humans are going to call the function, we don't need to give it a name. We call it a _callback_ function because we call addEventListener, and then addEventListener calls back with the function we passed it as an argument. The function goes off in a loop and then comes back to us, like a boomerang.

When a keydown event happens, the browser will pass that event as an _argument_ to our anonymous function. Our function will call preventDefault() on the event, which is itself a property of the event, and the keypress will in this way be intercepted.

This is the normal way to use callbacks, but to be clear, we could have done exactly the same thing with a non-anonymous function:

```javascript
function preventor(bob) {
  bob.preventDefault();
}

document.body.addEventListener("click", preventor);
```

When the document registers a click event, it will call preventor, and pass the click event to preventor. preventor internally represents the click event as bob, and it will call preventDefault() on bob.

### another syntax for function expressions

There is another, newer syntax for function expresions which you'll see a lot in the wild, called an arrow or fat-arrow function. I don't want to give you information overload, so I won't go into minutiae, but the gist is that they use => fat arrow syntax instead of the function keyword:

```javascript
document.body.addEventListener("click", event => event.preventDefault);
```

These are meant to be timesavers, and that means that, depending on how simple your function is, they can be more or less barebones. The version above is the most barebones it can be. For now, know that whenever you see a fat arrow like that, you are looking at a function expression, or arrow function. You can pick up the finer points in the future.

# Today's challenge
Wow, we've covered a lot of information. Today I want you to write your first function. The function will take no parameters, and will print a random letter of the alphabet, in lower case, to the console. It should be called randomLetter or something like that (whether you declare it or assign an expression to a variable is up to you). 

There's a fair bit you need to do to make a function print a random letter so I've written some starter code. I've also got some recommendations on how to finish the function. Here's the starter code:

```javascript
  const min
  const max
  const variance = max - min
  const randomness = Math.floor(Math.random*variance)
  const randomInRange = randomness + min
```

randomInRange would be a number in between min and max, if only these were numbers. As it is, it will throw an error. To complete the function, you should look into the String.fromCharCode function, and try to make it work. You should also check out the ASCII table. This should be a good introduction to reading online resources. MDN is always a solid choice if you see it in a google search. 

p.s. notice that I used constants. Constants are a good idea if you know you aren't going to reassign the variable later, because it means that, if you do reassign later, the program will throw an error, with a line-number, rather than just not working in some obscure way. Conversely, though, if you're struggling with a problem, and you aren't _sure_ whether you'll reassign or not, it's probably best not to encumber yourself with constants.
