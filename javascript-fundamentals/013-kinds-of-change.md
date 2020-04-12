# Two kinds of change

One of the functions of variables is to let us make comparisons. If we specify a variable at time t, and then do some things, we can track changes by comparing the value of our variable at different times.

Because variables are like names, people often make a mistake about variables that they also make about words: thinking about the word or variable as if it is the thing it refers to. In fact, however, this isn't right. While it is a tautology that all apples are apples, it is, at least on certain views, not a tautology that every reference of the word 'apple' is an apple - even if we think that statement is definitely true, it isn't a tautology. Anyway, there's a tangent lurking around the corner here. The upshot, for coding, is that the value of a variable can change in two ways:

- the thing the variable points to can change (this is called 'mutation')
- the variable can be made to point to a new thing (this is called reassignment)

## mutation

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
- boolean (true and false)
- undefined
- symbol

None of these values can be mutated. If you assign them to a variable, and then change the value of that variable, the variable is pointing to a different value.

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