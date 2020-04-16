# Review, arrow functions and namespace
Today we're going to do three relatively quick things. First, a review of what we've learnt about functions. Second, a bit about arrow function syntax. And finally, an exercise about using the command line. 

## Part 1: Functions review

Today we're going to do a quick review of everything you know about funcions - try just making a list, from memory. I have my own sample list below, which includes things I've taught you, so you can consult it once you've made yours, and compare the two.

<details>
<summary>Functions</summary>
- difference between expressions and declarations
- possibility of arrow syntax
- what are side effects
- what are return values
- how does a callback work?
- what's the difference between adding brackets to the end of a function and not?
</details>

## Part 2: How not to mess up arrow functions

basically arrow functions have a single, basic syntax, and then depending how simple your function is, you can omit various parts of the syntax. Including them will never break the function, but removing them sometimes will. Here's a basic arrow function

```javascript
(n) => { return n ** 2 }
```

There's three things to notice about this:
- there are brackets around the parameter.
- there are curly braces around the function body
- there is an explicit return statement

In various circumstances, these can each be removed if you want to type less characters.

The brackets around the parameter can be removed if you have exactly one parameter. In the example above, they are superfluous. But if we had two parameters, or no parameters, we would need to include brackets around the parameter field.

The curly braces can be omitted if you only have one line (actually, one expression). However, if you have multiple lines, you will need curly braces to delimit the function body.

Similarly, the return statement can be omitted if you only have one line. If you only have one line, the default return value of the function is the return value of that line. However, if you have multiple lines, the default return value of the function is ```undefined```. 

People often do apply these rules in the wild. Programers are a lazy bunch. One place to expect arrow functions is as the arguments to higher order array functions:

```javascript
[1, 2, 3].map(n => n * 100)
```

It creates a relatively clean syntax in an expression that would otherwise be full of brackets, curly-braces, and keywords.

## Part 3: explor the command line with mv to learn about namespace