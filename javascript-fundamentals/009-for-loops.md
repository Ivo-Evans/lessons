# For-loops

For-loop are a way of 

1. doing something  
1. until something is false

But despite this two-part purpose, they have four parts. This is an empty for-loop:

```javascript
for ( ; ; ) {

}
```

It's valid JavaScript, but it won't do anything. Here it is with the four parts annotated:

```javascript
for ( initialisation ; condition ; final-expression ) {
 statement
}
```

I'll briefly describe these four parts, and then we'll dissect an example. People don't generally know the names of the parts, so you shouldn't worry about memorising them. Just focus on trying to understand their purposes.

1. the __initialisation__, a piece of code run only once, when the loop begins. It is frequently used to declare a variable 
1. the __condition__. This accounts for the while (or until) mentioned above. After every iteration, the condition will be evaluated. If it has become false, the loop will not run again. 
1. The __final-expression__. This is run once at the end of every iteration of the loop. It is frequently used to increment the variable declared in the initialisation.
1. The __statement__. This is the thing you 'do' on every run of the loop, and, typically, where you express your purpose in code for creating the loop.

Each of these four parts is optional - the empty for-loop we declared above was valid, albeit useless, code. 


## rotate()
I'll write a function which rotates an array according to a numeric argument given to it. By this I mean that you could do this:

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
console.log(rotate(numbers, 2))
// [3, 4, 5, 6, 7, 8, 9, 10, 1, 2]
```

Here it is:

```javascript
function rotate(array, times) {
  array = [ ... array] // this line duplicates the array, to avoid mutating the input and make rotate() a pure function. It's not directly relevant for today, it's just good practice.
  for(let i = 0; i < times; i++) {
    array.push(array.shift())
  }
  return array;
}
```

This function's for-loop is a pretty-typical example. The _statement_ expresses the thing we want to do on each iteration of the loop, rotate the array by one. The top three conditions, meanwhile, are all for administration of the loop. The first one _declares_ a counter. The third one _increments_ the counter. And the second one says what needs to be false for the loop to stop running. 

## for-loops v.s. the higher order functions: fisticuffs
To be honest, while the example above is a typical example of for-loop syntax, it isn't _perfectly_ typical. The most common use for a for loop is to do something _once for every element of an array_, just like the higher-order functions we considered in the last lesson. Used to loop through an array, a for-loop looks like this:

```javascript
function customForEach(array, callbackFunction) {
  for(let i = 0; i < array.length; i++) {
    callbackFunction(array[i])
  }
}
```

The iterated variable is used to represent the _index_ of an array, and the exit condition is the index going out of the bounds of the array. 

__In general,__ it is better to use the higher-order array functions when you can, because they are considered to be cleaner and to help you avoid repetition. For-loops are older, and feel clunkier to a modern programmer. The higher-order functions were created to expedite common for-loop tasks. 

That said, there are some situations when you might want to use a for-loop. Here are three:

- you aren't actually looping through an array
 > ... because there is no data collection at all. This is the situation with the rotate() function we wrote earlier - we were looping through the numbers from 0 to the times parameter, but since there's no range data type in javascript, we can't use a higher order function on it. Another example is doing something once for every day until a certain point - although the dates are an ordered collection, there's no data type to represent that collection.   
 > ... because you've inherited an array-like value from the DOM which isn't actually an array, and for which the higher-order array functions are not available (see part 2 of this guide). 
- You are trying to optimise for speed
> Higher order functions generally do one job. If you want to do five things to an array, you coul do it with five higher-order functions, and then the array would be iterated through five times. On the other hand, if you did five things on each iteration of a for-loop, you would only have to iterate once, thus saving processing power. Understand, though, that speed is not always the priority. Computers are very fast anyway.
- You want your code to be backward-compatible, and you don't want to transpile it
> older environemnts don't support the higher-order functions. However, if you really want to write an application that works on Internet Explorer 10 (circa 2012) you can use a program like BabelJS, which 'transpiles' your code down into code that older browsers can understand. 

## An honorary mention to the for-loop's siblings

Before we close I should mention that there are some other for-loop like structures in JavaScript, for...of, for...in, and while. Of these, while loops are probably the most useful:

```javascript
while(x) {
  y
}
```


## Challenge - factorialise this

Ok, now I'm going to ask you to write a function that uses a for-loop of your own. The function should take a positive integer as an argument and return the factorial of that integer. The factorial of an integer is the integer times every number in between it and 1, inclusive. In maths (but not in programming) you indicate it with an exclamation mark.

  4! = 1 * 2 * 3 * 4 = 24

If possible, make your factorial function take up five lines or less, but don't worry about this at first. First write the function, and then refactor it to try to make it better.