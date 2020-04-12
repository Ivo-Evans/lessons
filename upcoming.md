
# overview of lexical environment and challenge

- overview of tokens
  - value 'literals'
  - identifiers
  - operators
  - keywords
  - comments
  - semi-colons
- challenge
  - write a function that takes an argument, finds the factorial of the argument, and prints it to the console
  - use the JavaScript keyword `for`


# - recursion

- weirdly enough, a function can call itself inside its definition
- this leads to some interesting and sometimes confusing results
- you need to specify a 'base case', or a situation in which the function does not call itself.
- to specify a base case, you need to build some branching logic into your function, so that, in one situation, it goes one way, and in another situation, it goes another way.
- when the function does call itself, you might want to think about what arguments you give it - you don't need to give it the same ones you gave it on the last pass
- rewrite your factorialising program to use recursion instead of a for-loop, and to return its result
- extra-challenge: - the command line: launching programs: vscode or editor of choice

# Appendix: how recursion actually works: the call stack

# closures and variable scope

- explanation
- the lobster cage - with a picture
- challenge: debug my functions!
