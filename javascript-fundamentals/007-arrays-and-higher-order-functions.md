# Arrays
An _array_ is a data type in JavaScript. It is nothing more than a list, where you can use the place of an item in the list to talk about the item. Any kind of data type, including arrays, can be an array item, or array _element_. Therefore, arrays are a reference type.

An item's place in the list is called its _index_. You can look up a single index with square brackets, and a range with the functin slice(), which is called on the array. When you give it no arguments, slice() simply returns a copy of the array.

But before you start doing that, there's something you need to know about array indexes! The counting starts from 0. So, say we have an array called myArray - the first element could be accessed with myArray[0], and the second with myArray[1].

Arrays always have a length property. If we write myArray.length, we get the length of the array. Accordingly, we can use the length property to access an array from the back

```javascript
myArray[myArray.length - 1]
// this is the final item of the array because arrays are 0-indexed
```

o-indexing meme

After all this, you're probably wondering how you can make an array! You use square brackets to indicate the beginning and end of an array literal, and commas to separate the elements. Whitespace is optional, so you can put each item on a new line if you find that clearer.

```
  let myActualArray = [1, 2, '5', ['nested', 'array', 'aka', '2d array']]
```

## The four basic array functions
There are four really basic functions for changing arrays: push, pop, shift and unshift. These all add or remove from the back or front of an array respectively.

push takes an argument and adds that argument onto the back of an array. pop doesn't take an argument, but removes an element from the back of the array

```
myActualArray.pop()
myActualArray.push('alabaster')
```

shift() takes an element away from the front of the array. unshift() can add it, or anything you want, back on again.

All four of these functions 'mutate' the array, i.e. change the array itself - a detail which might not seem relevant now but which will come up again and again as you're learning.

Finally, note that, given the choice, it is better to add or remove from the end of the array than from the beginning, because if you edit the beginning of the array, the indexes of everything else will be thrown off. Strive, always, for simplicity in your programs.

Don't stress about remembering all of these now. They'll crop up again.

## The higher order array functions
There are also a number of 'higher order' array functions. These are the prefferred methods for doing something once for every element of an array, and returning a result. Here's an example, forEach:

```javascript
myActualArray.forEach(function(element) {
  if (typeof element !== 'number') {
    console.log(element)
  }
})
```
There's a lot going on here, but we can break it down. Let's work from the outside inwards. forEach takes an argument in between its opening and closing brackets. This _argument_ is a function expression, which has a parameter called element (we could have called it anything we liked). For every element in the array, forEach will call the function that was provided to it as an argument, and give _that_ function the particular array element. This is why we call the higher order functions 'higher order' - they are functions which call a function once for every element of an array.

Now all that's left from the above is to understand the function we gave forEach as an argument.
<details>
<summary>Expand</summary>
 It uses three new things:

- an if-statement
- the typeof keyword
- !==

An if-statement does what you would expect. The syntax is ```if () {}```. You put the criterion inside brackets, and if it evaluates to true, the part inside curly braces evaluates. The part inside curly brackets is called a __block__.

The typeof keyword also does what you'd expect: it tests for data types, and returns a string. However, there are a few gotchas that you'll encounter as you progress. try

```javascript
typeof myActualArray
typeof push
```

Not what you'd expect right?

Finally, we have !==. This is the opposite of ===. It means 'does not equal'
</details>

<details><summary>Refactoring the above to use an arrow function</summary>
Note that we could have done the same thing as above with an _arrow function_, and that's normally how you'll see the higher order functions:

```javascript
myActualArray.forEach((element) => {
  if (typeof element !== 'number') {
    console.log(element)
  }
})
```
</details>

// The index parameter of the callback

Here are the most important higher order array functions. Again, don't stress about memorising them, just try to peruse the list, and remember that they are there, for you to look up in the future

|name |what it does | what its for |
|-----|--------------|------|
|forEach|passes each element to callback one by one|doing something once for each item of an array|
|map|passes each element to callback one by one, records callback's return value, and uses each return value to return a modified version of the original array|turning one array into another array of the same length|
|filter|passes each element to callback one by one. If the callback returns 'true', push the original element onto an array in filter. Once every element has been passed to callback, return the array in filter|selecting a subset of an array|
|sort|If given no argument, sorts everything as if they are strings. If given a callback, uses the numeric return of the callback to do a sorting operation.|sorting an array|
|reduce|Takes two arguments. The first is a callback, and the second is an initial value which the callback will modify. The callback should take at least two parameters, where the first is the current running total, and the second is the element.|using every item of an array to generate a single value of any data type|
|every|Starts off with the value true. Goes through elements. If callback returns a false or falsy value, the function returns false. Otherwise, it returns true.|finding out if something is true of every element in an array|
|some|Starts off with the value false. Goes through elements. If callback returns a true or truthy value, the function returns true. Otherwise, it returns false. |finding out if something is true of at least one element in an array|

These functions are all intended to be pure. You can change the array by naming it inside the callback, but the functions themselves won't change the array. Internally, they make copies of arrays, do their work on those copies, and then, where relevant, return the copies.

# Challenges
In this lesson, I've mentioned a number of functions and properties:

- length (this is a property not a function)
- slice()
- push()
- pop()
- shift()
- unshift()
- forEach()
- map()
- filter()
- sort()
- reduce()
- every()
- some()

Let's get some practice using some of them

## Challenge 1

I generated a massive array of numbers, because I have a flair for fun. You can find it in 007-data.

Using the functions and properties discussed above, find out:
- how long it is
- what elements are in between indexes 3000 and 3005
  - bonus: use a function to extract the first five elements from the array. Do you notice anything strange?
- whether every item in the array is actually a number
- wheher there are any negative numbers in the array
- how many elements of the array are even
- what the sum of the array divided by 1000 is (note that the reduce function is a little harder to use than some of the others. [Here](https://www.w3schools.com/jsref/jsref_reduce.asp) is a link)

Note: if repl.it is being too slow, you might want to write the functions in repl.it, but store the array in your browser console and then copy the functions over there to test them.

## Challenge 2

- write an array literal composed of strings
- use a higher-order function to return the array all in capitals. There is a function for capitalising strings.
- use sort() to sort the array
- write an array literal composed of numbers - make sure you have a good spread of sizes and that the array is at least ten items long - and then sort it.

## Bonus challenge

Most of the callbacks to the higher order array functions take an extra parameter we haven't used here, which represents the index of the element. Can you use this extra parameter to console log every index of the array ```sample```?

```javascript
const sample = [1, 1, 1, 1, 1, 1]
```

Can you use the index parameter on the above array to return the below array?

```javascript
[0, 1, 2, 3, 4, 5]
```