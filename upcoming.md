# functions
  - what are they

  - syntaxes
    - declarations
    - expressions
      - trad
      - arrow
    - expressions are technically anonymous, but they can be saved to variables, so they're effectively the same

  - challenge
    - I've written a function which generates a random number in a range. I want you to _use_ that function inside a function that prints a random number to the console. I've minimised this in case you want to have a go at writing your own randomInRange function, but I don't expect you to do something like that on lesson 3. 

```
function randomInRange(min, max) {
  let variance = max - min
  let randomness = Math.floor(Math.random*variance)
  return min + randomness
}
```
    - write a function which generates a random letter of the alphabet each time it is called, and logs that letter to the console. In your function, you might want to use
      - String.fromCharCode() https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode
      - Math.random ()
      - Math.floor() or Math.ceil()
      - the multiplication operator
    - If you're using String.fromCharCode(), you might want to consult the ASCII table

# overview of lexical environment and challenge
- overview of tokens
  - values
  - identifiers
  - operators
  - keywords
  - comments
  - semi-colons
- challenge
  - write a function that takes an argument, finds the factorial of the argument, and prints it to the console
  - use the JavaScript keyword ```for```


# side effects v.s. return values
	- well done on making your program
	- functions were created as programs which take an input and return an output. A 'pure' function is one which does this without changing the state of anything outside the function.
	- changes to state outside the function are called 'side effects'
	- many functions nowadays actually exist _for_ their side effects
	- console.log is a good example. It's purpose is to log something to the console, but doing so is a side effect
	- you can save a return value to a variable, or feed it dirctly to another function.
	- let's call console.log(console.log('hello, world'))
	- the outer console log logs undefined, and the inner one logs 'hello, world'. This is because the inner console log has an _undefined_ return value, which is what the outer one has to work with.
	- undefined is one of the 7 primitive data types in JavaScript
	- Now let's look at the function you wrote yesterday.
	- Its main output right now is to console log something - this is a side effect. Currently it has an undefined return value.
	- you can specify its return value with the return keyword - nothing after this keyword in the function will be evaluated, because the function will simply exit
	- modify your function so that it returns its result, instead of console logging its result
	- console log the return value of your function.
  - extra challenge: the command line: mv as an opportunity to learn the concept of namespace

# - recursion
  - weirdly enough, a function can call itself inside its definition
  - this leads to some interesting and sometimes confusing results
  - you need to specify a 'base case', or a situation in which the function does not call itself. 
  - to specify a base case, you need to build some branching logic into your function, so that, in one situation, it goes one way, and in another situation, it goes another way. 
  - when the function does call itself, you might want to think about what arguments you give it - you don't need to give it the same ones you gave it on the last pass
  - rewrite your factorialising program to use recursion instead of a for-loop, and to return its result
  - extra-challenge: - the command line: launching programs: vscode or editor of choice
