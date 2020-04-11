# Doing maths

One of the fundamental features of a programming language is maths, and so they're important operators to know, even if modern programming isn't all that mathsy. They're also a good thing for a beginner to learn, because maths in programming (unlike, e.g., the concept of truth) are imported directly from the outside world.

Here are the JavaScript mathematical operators:

```
**
*
/
%
+
-
```

## The four most common operators

The four most common operators are +, -, \* and /

They follow the order of operations in maths (PEMDAD/BIDMAS). Therefore, in the expression

    6 + 6 / 2

You can expect to get 9 back as a result, unless you use brackets to tug at the interpretation of the expression.

To find the result, you do not need to use an equals sign. The mathematical operators resolve all on their own, when they can. For instance, console logging 6 \* 2 will return 12

## 'Floating point' numbers

Numbers in between integers - numbers with decimal places - are called floating point numbers.

Interestingly, in every programming language that I know of, they're inexact by default:

    0.1 + 0.2
    // 0.30000000000000004

the // is JavaScript notation for a comment - i'll use it in these lessons to give expected values

Computers represent numbers in _binary_ or base two - as series' of 1 and 0 - and this, in combination with a limited number of _bits_, or places for 1's and 0's, means that some numbers literally cannot be represented.

## Exponentiation operator

JavaScript has recently gotten an upgrade in the form of the exponentiation operator:

    2**3
    // 8

## modulo/remainder

The final operator is the remainder operator. In other programming languages it is called the **modulo** operator. The remainder operator finds the remainder after dividing one number by another. For instance,

```
	21 % 5
	// 1
```

21 cannot be divided by 5 and yield an integer. However, 20 can be divided by 5, with one left over: that is the modulus of that operation. By the same token, 21 / 5 is 4.2 ; 4.2 rounded down is 4, with five 0.2's left over - it is those 5 0.2's that the remainder operation hoovers up.

I find the modulo/remainder operation interesting because it is not pure like other mathematics: something is lost. 5/2 creates 2.5 neatly, but if you divide 21 by 5 with the aim of leaving integers, while you are left with two results (a quotient and a remainder), you throw one of them away, thus subtracting from the purity of the system. This property of modulus operations makes them useful to cryptographers: reversing a modulus operation on a very high number is difficult, because not all of the relevant information is available in the result.

Another interesting property of the modulus operation is that its result will never be higher than its divisior.

```
20 % 5 // 0
21 % 5 // 1
22 % 5 // 2
23 % 5 // 3
24 % 5 // 4
25 % 5 // 0
```

For this reason, the modulo operation is a great way to determine whether a number is even in languages that do not have a built in function for this (like JavaScript).

```
21 % 2 // 1
22 %% 2 // 0
```

Finally, note that that there is a difference between modulo and remainder operations, which emerges when you try to use them on a minus number. _Remainder_ operations are interested in the absolute value of a number, while _modulus_ operations are interested in the number itself. Thus, in Ruby or Python,

```
-21 % 5 # 4 (Ruby/Python comment syntax is a hash)
```

But in JavaScript,

```
-21 % 5 // -1
```

So what's up? -21 / 5 is -4.2. Ruby, performing a _modulo_ operation, subtracts 0.8 from each -4.2 to make -5, and then multiplies what it subtracted by 5, to make 4. JavaScript, performaing a remainder operation, subtracts -0.2 from each -4.2 (to make them -4) and then multiplies what _it_ subtracted by 5, to make -1.

## == - an assertion of equality - really a logical relationship

You can use == to see whether two things are equal. This is, really, a _logical_ relationship, not a mathematical one. It always returns `true` or `false`, not numbers, and it can be called on data of any type - sometimes with surprising results.

## Challenge

The challenge today isn't anything to do with maths. I just want you to experiment with the command line with three commands: pwd, ls and cd.

But first, what is the command line?

Way back in the day, computers didn't have windows or pictures (in fact, bringing 'windows' to the masses was Microsoft's big innovation). There were literally just lines of text, like you see in your terminal. Nowadays, the terminal is inside the windowing system, and not vice versa, although there are also some graphical apps that you can enter in your terminal, like nano. But the upshot is this: the terminal is a way to navigate your computer, make changes to the filesystem, and launch applications - even applications with no _graphical_ manifestation.

The commands I'm going to teach you today are all related to the first of these purposes: navigation. They are 'safe' commands, because they are just about travelling and looking.

So, open up your terminal, enter pwd, and hit enter.

pwd stands for 'print working directory' and it is where you are now.

Now type ls.

ls stands for 'list' and it lists the content of the working directory. However, you can also give it _arguments_, which modify its usage. For instance,

```
	ls -a
```

lists hidden files, such as system files, as well as visible ones.

You can also provide the name of a folder which is in the current working directory as an argument to ls, and then ls will list the contents of _that_ directory.

Finally, cd stands for change directory. Let's say that after using ls, you know that your working directory contains my-folder. You can use cd to move into it

```
	cd my_folder
	pwd
```

what if you want to go back? I'm going to teach you two ways. The tilde (~) is an alias for your 'home' directory. Wherever you are in the filesystem, ~ means 'your home', whatever that happens to be. I believe that on macs home is the desktop.

Another symbol is two dots(..). This means 'this directory's parent directory'. It allows you to go up a single layer, relative to where you are now.

The challenge, if you can call it such, is just to move around your filesystem, getting to know these three commands. They'll pay dividends!
