---
title: "Receiving Functions as Arguments"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 4
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

The previous section illustrates how a function can be passed to another
function as an argument. This section takes the opposite perspective to
*write* functions that can take other functions as arguments.

## Example: A Generic Input Validator

Our first example will be a generic input validator. It asks the user for some
input, using the `prompt` parameter for the text of the question. A second
parameter receives a function that does the actual work of validating the
input.

{{% notice blue Example "rocket" %}}
```javascript {linenos=true}
const input = require('readline-sync');

function getValidInput(prompt, isValid) {

    // Prompt the user, using the prompt string that was passed
    let userInput = input.question(prompt);

    // Call the boolean function isValid to check the input
    while (!isValid(userInput)) {
    console.log("Invalid input. Try again.");
    userInput = input.question(prompt);
    }

    return userInput;
}

// A boolean function for validating input
let isEven = function(n) {
    return Number(n) % 2 === 0;
};

console.log(getValidInput('Enter an even number:', isEven));
```

**Sample Output**

```console
Enter an even number: 3
Invalid input. Try again.
Enter an even number: 5
Invalid input. Try again.
Enter an even number: 4
4
```

When we call `getValidInput` on line 22, we pass it the string
`'Enter an even number:'`, which gets assigned to the `prompt`
parameter.

Notice that we also pass in the function `isEven` (with no arguments).
This gets assigned to the `isValid` parameter.
{{% /notice %}}

The function `getValidInput` handles the work of interacting with the user, while allowing the validation logic to be customized. This separates the different concerns of validation and user interaction, sticking to the idea that *a function should do only one thing*. It also enables more reusable code. If we need to get different input from the user, we can simply call `getValidInput` with different arguments.

{{% notice blue Example "rocket" %}}
This example uses the same `getValidInput` function defined above with a different prompt and validator function. In this case, we check that a potential password has at least 8 characters.

```javascript
const input = require('readline-sync');

function getValidInput(prompt, isValid) {

    let userInput = input.question(prompt);

    while (!isValid(userInput)) {
    console.log("Invalid input. Try again.");
    userInput = input.question(prompt);
    }

    return userInput;
}

let isValidPassword = function(password) {

    // Passwords should have at least 8 characters
    if (password.length < 8) {
    return false;
    }

    return true;
};

console.log(getValidInput('Create a password:', isValidPassword));
```

**Sample Output**

```console
Create a password: launch
Invalid input. Try again.
Create a password: code
Invalid input. Try again.
Create a password: launchcode
launchcode
```
{{% /notice %}}

{{% notice blue "Try It!" "rocket" %}}
1. Use our `getValidInput` function to ensure user input starts with "a".
1. Create another validator that ensures user input is a vowel.

You can find the above function in the `getValidInput.js` file within your `javascript-projects` repository!
{{% /notice %}}

## Example: A Logger

Another common example of a function using another function to customize its behavior is that of logging. Real-world applications are capable of logging messages such as errors, warnings, and statuses. Such applications allow for log messages to be sent to one or more destinations. For example, the application may log messages to both the console and to a file.

We can write a logging function that relies on a function parameter to determine the logging destination.

### A Simple Logger

{{% notice blue Example "rocket" %}}
The `logError` function outputs a standardized error message to a location determined by the parameter `logger`.

```javascript {linenos=true}

let fileLogger = function(msg) {

    // Put the message in a file
}

function logError(msg, logger) {
    let errorMsg = 'ERROR: ' + msg;
    logger(errorMsg);
}

logError('Something broke!', fileLogger);
```
{{% /notice %}}

Let's examine this example in more detail.

There are three main program components:

1. Lines 1-5 define `fileLogger`, which takes a string argument, `msg`. We have not discussed writing to a file, but Node.js is capable of doing so. 
1. Lines 7-10 define `logError`. The first parameter is the message to be logged. The second parameter is the logging function that will do the work of sending the message somewhere. `logError` doesn't know the details of how the message will be logged. It simply formats the message, and calls `logger`.
1. Line 12 logs an error using the `fileLogger`.

This is the flow of execution:

1. `logError` is called, with a message and the logging function `fileLogger` passed as arguments.
1. `logError` runs, passing the constructed message to `logger`, which refers to `fileLogger`.
1. `fileLogger` executes, sending the message to a file.

### A More Complex Logger

This example can be made even more powerful by enabling multiple loggers.

{{% notice blue Example "rocket" %}}
The call to `logError` will log the message to both the console and a file.

```javascript
let fileLogger = function(msg) {

    // Put the message in a file
}

let consoleLogger = function(msg) {

    console.log(msg);
}

function logError(msg, loggers) {

    let errorMsg = 'ERROR: ' + msg;

    for (let i = 0; i < loggers.length; i++) {
    loggers[i](errorMsg);
    }
}

logError('Something broke!', [fileLogger, consoleLogger]);
```
{{% /notice %}}

The main change to the program is that `logError` now accepts an *array* of functions. It loops through the array, calling each logger with the message string.

As with the validation example, these programs separate behaviors in a way that makes the code more flexible. To add or remove a logging destination, we can simply change the way that we call `logError`. The code *inside* `logError` doesn't know how each logging function does its job. It is concerned only with creating the message string and passing it to the logger(s).

## A Word of Caution

What happens if a function expects an argument to be a function, but it isn't?

{{% notice blue "Try It!" "rocket" %}}
```javascript
function callMe(func) {
    func();
}

callMe("Al");
```
{{% /notice %}}

{{% notice green Question "rocket" %}}
What type of error occurs when attempting to use a value that is NOT a function as if it were one?
{{% /notice %}}