Things I haven't covered yet (notes for self)

- semi-colons in JavaScript: statements and expressions

- Doing maths with the mathematical operators
	- walk through operators
	- floating point imprecision
	- explain modulo/remainder
	- brackets work just like in Maths
	- order of operations/PEMDAS

- operators - assignment operators
	- assignment is right-to-left

- variables, functions and identifiers
	- saving values to a state: variables
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
		- research the keyword if
		- research the keyword for (hint: google JavaScript for-loop)
		- write a function which takes a number n and tells me whether that number is a prime number. If the number you give it when you call it is is a prime number, the function should print 'prime' to the console. If it isn't, it should print 'not prime'. 

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


Other things to splice in:
- the command line: pwd, cd and ls - move around for a bit
- the command line: mkdir, rm and touch
- the command line: mv as an opportunity to learn the concept of namespace
- the command line: launching programs: vscode or editor of choice
