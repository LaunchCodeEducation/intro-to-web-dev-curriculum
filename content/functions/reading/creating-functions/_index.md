---
title: "Creating Functions"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

While using the functions built into JavaScript is useful, the most powerful aspect of functions is the ability of programmers to create their own.

There are several ways to define functions in JavaScript. We will introduce one technique in this chapter and a second technique in the next.

## Function Syntax

To create a function, use the following syntax:

```javascript
function myFunction(parameter1, parameter2,..., parameterN) {

    // function body

}
```

Here, `function` is a keyword that instructs JavaScript to create a new function using the definition that follows. Since `function` is a keyword, it may not be used elsewhere, for example as the name of a variable.

Following `function` is the **function name**, which is `myFunction` in the generic example above. The function name is determined by you, the programmer, and should therefore follow best practices. In particular, function names should use camel case and have descriptive names. We will have more to say about naming functions near the end of this chapter.

Following the function name, we define **parameters** within the parentheses. Think of parameters as variables that can be used only within the function itself. The number and names of the parameters are determined by the programmer, based on what they want the function to do. A function may be defined with several parameters, or no parameters at all.

{{% notice blue Note "rocket" %}}
Many programming languages require you to state which data type each parameter should be (for example, string or number). In such languages, if you try to call a function with a parameter of incorrect type, an error results.
{{% /notice %}} 

JavaScript *does not* allow you to specify the types of parameters, though the JavaScript extension TypeScript does. We will learn a bit of TypeScript later on.

After the parameters and closing parenthesis, within curly brackets, `{ }`, is the **function body**. This is where the actions that the function should carry out are defined. The function body can consist of any amount of code.

### An Example

Let's see function syntax in action. We first consider a program that prints an array of names.

```javascript
let names = ["Lena", "James", "Julio"];

for (let i = 0; i < names.length; i++) {
    console.log(names[i]);
}
```

Following this pattern, we can create a function that prints *any* array of names.

```javascript
function printNames(names) {
    for (let i = 0; i < names.length; i++) {
        console.log(names[i]);
    }
}
```

Breaking down the components of a function using our new terminology gives us:

- **Function name**: `printNames`
- **Parameter(s)**: `names`
- **Body**: 

```console
for (let i = 0; i < names.length; i++) {
    console.log(names[i]);
}
```

Notice that there is nothing about this function that forces `names` to actually contain names, or even strings. The function will work the same for any array it is given. Therefore, a better name for this function would be `printArray`.

Our function can be used the same way as each of the built-in functions, such as `console.log`, by calling it. Remember that calling a function triggers its actions to be carried out.

```javascript
function printArray(names) {
    for (let i = 0; i < names.length; i++) {
        console.log(names[i]);
    }
}

printArray(["Lena", "James", "Julio"]);
console.log("---");
printArray(["orange", "apple", "pear"]);
```

**Console Output**

```console
Lena
James
Julio
---
orange
apple
pear
```

This example illustrates how functions allow us to make our code **abstract**. Abstraction is the process of taking something specific and making it more general. In this example, a loop that prints the contents of a specific array variable (something specific) is transformed into a function that prints the contents of *any* array (something general).

## Defining and Calling

When we define a function, we are making it available for later use. The function does not execute when it is defined; it must be *called* in order to execute. This is not only a common point of confusion for new programmers, but can also be the source of logic errors in programs.

Let's see how this works explicitly.

{{% notice blue "Try it!" "rocket" %}}
What happens if we define a function without calling it?

```javascript
function sayHello() {
    console.log("Hello, World!");
}
```
{{% /notice %}}

{{% notice green Question "rocket" %}}
What is printed when this program runs? 
{{% /notice %}}

In order for a function to run, it must be explicitly *called*.

{{% notice blue Example "rocket" %}}
```javascript
function sayHello() {
    console.log("Hello, World!");
}

sayHello();
```

**Console Output**

```console
Hello, World!

```
{{% /notice %}}