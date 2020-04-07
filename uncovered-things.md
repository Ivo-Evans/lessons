Things I haven't covered yet (notes for self)

- semi-colons in JavaScript: statements and expressions
- comments

- Doing maths with the mathematical operators
	- walk through operators
	- floating point imprecision
	- explain modulo/remainder
		- difference from 'true' mathematical operators - something is lost
		- cryptography
		- finding even numbers
	- brackets work just like in Maths
	- order of operations/PEMDAS

- operators - assignment operators
	- assignment is right-to-left

- variables, functions and identifiers
	- saving values: variables
		- let, const and var (for now just use let)
		- undeclared variables (a big no no, but possible)
	- notational conventions - pascalCase in JavaScript
	- functions
		- function declarations
			- parameters as a kind of value
		- function expressions
			- traditional
			- arrow functions - survey of the syntax
		- function expressions saved to variables


- overview of the lexical environment of a JavaScript program and challenge
	- overview of tokens
		- values
		- identifiers
		- operators
		- keywords
			- let is an example of a keyword
	- challenge
		- research the keyword for (hint: google JavaScript for-loop)
		- write a function that takes an argument, and finds the factorial of it.

- Theoretical v.s. practical considerations in the construction of functions: side effects v.s. return values
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

- recursion
  - weirdly enough, a function can call itself inside its definition
  - this leads to some interesting and sometimes confusing results
  - you need to specify a 'base case', or a situation in which the function does not call itself. 
  - to specify a base case, you need to build some branching logic into your function, so that, in one situation, it goes one way, and in another situation, it goes another way. 
  - when the function does call itself, you might want to think about what arguments you give it - you don't need to give it the same ones you gave it on the last pass
  - rewrite your factorialising program to use recursion instead of a for-loop, and to return its result

Other things to splice in:
- the command line: pwd, cd and ls - move around for a bit
- the command line: mkdir, rm and touch
- the command line: mv as an opportunity to learn the concept of namespace
- the command line: launching programs: vscode or editor of choice
