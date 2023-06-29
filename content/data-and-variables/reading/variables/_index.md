---
title: "Variables"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

One of the most powerful features of a programming language is the ability to manipulate variables. A **variable** is a name that refers to a value. Recall that a value is a single, specific piece of data, such as a specific number or string. Variables allow us to store values for later use.

A useful visual analogy for how a variable works is that of a label that *points to* a piece of data.

![A label, programmingLanguages, pointing to a the string value "JavaScript"](pictures/variable.png?classes=border)

In this figure, the name `programmingLanguage` points to the string value `"JavaScript"`. This is more than an analogy, since it also is representative of how a variable and its value are stored in a computer's memory.

With this analogy in mind, let's look at how we can formally create variables in JavaScript.

## Declaring and Initializing Variables With `let`

To create a variable in JavaScript, create a new name for the variable and precede it with the keyword `let`:

```javascript
let programmingLanguage;
```

This creates a variable named `programmingLanguage`. The act of creating a variable is referred to as **variable declaration**, or simply **declaration**.

Once a variable has been declared, it may be given a value using an **assignment statement**, which uses `=` to give a variable a value.

```javascript
let programmingLanguage;
programmingLanguage = "JavaScript";
```

The act of assigning a variable a value for the first time is called **initialization**.

The first line creates a variable that does not yet have a value. The variable is a label that does not point to any data.

![The name "programmingLanguage" with no arrow connecting it to data.](pictures/unassigned-variable.png?classes=border)

The second line assigns the variable a value, which connects the name to the given piece of data.

![A label, programmingLanguages, pointing to a the string value "JavaScript"](pictures/variable.png?classes=border)

It is possible to declare *and* initialize a variable with a single line of code. This is the most common way to create a variable.

```javascript
let programmingLanguage = "JavaScript";
```

{{% notice red Warning "rocket" %}}
You will see some programmers use ``var`` to create a variable in JavaScript, like this:

```javascript
var programmingLanguage = "JavaScript";
```

While this is valid syntax, you should NOT use ``var`` to declare a variable. Using ``var`` is old JavaScript syntax, and it differs from ``let`` in important ways that we will learn about later. When you see examples using ``var``, use ``let`` instead.

If you're curious, read about [the differences between var and let](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables#The_difference_between_var_and_let).
{{% /notice %}}

To give a variable a value, use the **assignment operator**, `=`. This operator should not be confused with the concept of *equality*, which expresses whether two things are the "same" (we will see later that equality uses the `===` operator). The assignment statement links a *name*, on the left-hand side of the operator, with a *value*, on the right-hand side. This is why you will get an error if you try to run:

```javascript
"JavaScript" = programmingLanguage;
```

An assignment statement must have the name on the left-hand side and the value on the right-hand side.

{{% notice green Tip "rocket" %}}
To avoid confusion when reading or writing code, say to yourself:

`programmingLanguage` is assigned `'JavaScript'`

or

`programmingLanguage` gets the value `'JavaScript'`.

Don't say:

`programmingLanguage` equals `'JavaScript'`.
{{% /notice %}}

{{% notice red Warning "rocket" %}}
What if, by mistake, you leave off `let` when declaring a variable?

```javascript
programmingLanguage = "JavaScript";
```

Contrary to what you might expect, JavaScript will not complain or throw an error. In fact, creating a variable without `let` is valid syntax, but it results in very different behavior. Such a variable will be a **global variable**, which we will discuss later. 

The main point to keep in mind for now is that you should *always* use `let` unless you have a specific reason not to do so.
{{% /notice %}}

## Evaluating Variables

After a variable has been created, it may be used later in a program anywhere a value may be used. For example, `console.log` prints a value; we can also give `console.log` a variable.

{{% notice blue Example "rocket" %}}
These two examples have the exact same output.

```javascript
console.log("Hello, World!");
```

```javascript
let message = "Hello, World!";
console.log(message);
```
{{% /notice %}}

When we refer to a variable name, we are **evaluating** the variable. The effect is just as if the value of the variable is substituted for the variable name in the code when executed.

{{% notice blue Example "rocket" %}}
```javascript
let message = "What's up, Doc?";
let n = 17;
let pi = 3.14159;

console.log(message);
console.log(n);
console.log(pi);
```

**Console Output**

```bash
What's up, Doc?
17
3.14159
```
{{% /notice %}}

In each case, the printed result is the value of the variable.

Like values, variables also have types. We determine the type of a variable the same way we determine the type of a value, using `typeof`.

{{% notice blue Example "rocket" %}}
```javascript
let message = "What's up, Doc?";
let n = 17;
let pi = 3.14159;

console.log(typeof message);
console.log(typeof n);
console.log(typeof pi);
```

**Console Output**

```bash
string
number
number
```
{{% /notice %}}


The type of a variable is the type of the data it currently refers to.

## Reassigning Variables

We use variables in a program to "remember" things, like the current score at the football game. As their name implies, variables can change over time, just like the scoreboard at a football game. You can assign a value to a variable and later assign it a different value.

To see this, read and then run the following program in a code editor. You'll notice that we change the value of `day` three times, and on the third assignment, we even give it a value that is of a different data type.

```javascript
let day = "Thursday";
console.log(day);

day = "Friday";
console.log(day);

day = 21;
console.log(day);
```

A great deal of programming involves asking the computer to remember things. For example, we might want to keep track of the number of missed calls on your phone. Each time another call is missed, we can arrange to update a variable so that it will always reflect the correct total of missed calls.

{{% notice blue Note "rocket" %}}
We only use `let` when *declaring* a variable, that is, when we create it. We do NOT use `let` when reassigning the variable to a different value. In fact, doing so will result in an error.
{{% /notice %}} 

## Check Your Understanding

{{% notice green Question "rocket" %}}
What is printed when the following code executes?

```javascript
let day = "Thursday";
day = 32.5;
day = 19;
console.log(day);
```

1. Nothing is printed. A runtime error occurs.
2. `Thursday`
3. `32.5`
4. `19`
{{% /notice %}}

{{% notice green Question "rocket" %}}
How can you determine the type of a variable?

1. Print out the value and determine the data type based on the value printed.
2. Use `typeof`.
3. Use it in a known equation and print the result.
4. Look at the declaration of the variable.
{{% /notice %}}

{{% notice green Question "rocket" %}}
Which line is an example of variable initialization? (*Note: only one line is such an example.*)

```javascript
1: let a;
2: a = 42;
3: a = a + 3;
```
{{% /notice %}}