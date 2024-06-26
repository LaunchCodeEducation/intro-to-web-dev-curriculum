---
title: "Naming Functions"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 7
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

As with variables, choosing good, descriptive names for the functions you write is important. It makes your code more readable, and therefore more maintainable and more bug-resistent.

## Use Camel Case

As with variables, use camel case. All functions in JavaScript should begin with a lowercase letter, with the first letter of subsequent words capitalized.

{{% notice blue Example "rocket" %}}
**Good**

- `const astronautCount = 7;`
- `const fuelTempCelsius = -225;`
- `let isReady = false;`


**Bad**

- `const AstronautCount = 7;`
- `const fuel_temp_celsius = -225;`
- `let is_ready = false;`
{{% /notice %}}

## Use Verb/Noun Pairs When Applicable

A function carries out an action, and it often produces some specific output or
effect. Therefore, using a verb/noun pair can go a long way toward making it
clear what a function does. A good verb can describe the action, and a good
noun can describe the output, or the object that is being affected by the
function.

{{% notice blue Example "rocket" %}}
**Good**

- `prepareForLiftoff`
- `fillFuelTank`
- `getCountdownStatus`
- `isReadyForLiftoff`

**Bad**

- `liftoff`
- `fillup`
- `countdownStatus`
- `isReady`
{{% /notice %}}

As we noted earlier, for boolean functions it is conventional that their names start with "is" or "has" whenever possible. 

Creating a verb/noun pair for a function name doesn't always make sense, but when it does, you should use this format to create a good, descriptive name.

## Use Descriptive Names

We have repeatedly reminded you to use descriptive names, but now we want to expand on this point. You should *prefer long, descriptive names over short, abbreviated names*. If you can read a function name and understand what it does from the name alone, then the function has a good name.

{{% notice blue Example "rocket" %}}
**Good**

- `convertCelsiusToFahrenheit`
- `isValidLaunchCode`
- `updateMissionControl`

**Bad**

- `convertC`
- `validCode`
- `msgToMC`
{{% /notice %}}

If you find yourself writing a comment to describe what your function does, consider whether a better name might remove the need for such additional explanation. The best function (and variable) names are those that are *self-documenting*---descriptive enough not to need further explanation. 

Using self-documenting names means that the code that *uses* your function will be more readable, since your explanatory comments are not visible where the function is used. Additionally, it is easy for comments to become inaccurate; when you update your code to change behavior, there is nothing forcing you to also update your comments. For this reason, some programmers live by the maxim, "Comments lie." While we won't go so far as to say that you should never use comments in your code, we *do* believe that comments should not be used to make up for poor function and variable names.

## Check Your Understanding

{{% notice green Question "rocket" %}}
Which is the BEST name for the following function?

```javascript
function myFunc(radius) {
    let area = Math.PI * radius**2;
    return area;
}
```

1. `area`
1. `calculateAreaOfCircle`
1. `circle`
1. `shape`

<!-- Solution: calculateAreaOfCircle -->
{{% /notice %}}