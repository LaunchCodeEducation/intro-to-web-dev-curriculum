---
title: "Studio: Functions"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # set by page reviewer
reviewerGitHub: # set by page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # Wed Jul 5 08:49:19 AM CDT 2023
---

The `reverse` method flips the order of the elements within an array. However, `reverse` does not affect the digits or characters within those elements.

{{% notice blue Note "rocket" %}}
The following studio can be found within the `javascript-projects/functions/studio` directory.
{{% /notice %}}

{{% notice blue Example "rocket" %}}
```javascript
let arr = ['hello', 'world', 123, 'orange'];

arr.reverse()
console.log(arr);
```

**Console Output**

```console
['orange', 123, 'world', 'hello']
```
{{% /notice %}}

What if we wanted the reversed array to be `['egnaro', 321, 'dlrow', 'olleh']`?

Let's have some fun by creating a process that reverses BOTH the order of the
entries in an array AND the order of characters within the individual elements.

Remember that a function should perform only one task. To follow this best
practice, we will solve the array reversal by defining two functions - one that
reverses the characters in a string (or the digits in a number) and one that
flips the order of entries in the array.

## Part One: Reverse Characters

In the *composing functions* section, we examined a function that [reverses characters in a string]({{< relref "../reading/composing-functions/_index.md#the-reverse-function" >}}) using the `split` and `join` methods. Let's rebuild that function now.
1. Define the function as `reverseCharacters`. Give it one parameter, which will be the string to reverse.
1. Within the function, `split` the string into an array, then reverse the array.
1. Use `join` to create the reversed string and *return* that string from the function.
1. Below the function, define and initialize a variable to hold a string.
1. Use `console.log(reverseCharacters(myVariableName));` to call the function and verify that it correctly reverses the characters in the string.
1. *Optional*: Use method chaining to reduce the lines of code within the function.

{{% notice green Tip "rocket" %}}
Use these sample strings for testing:

1. `'apple'`
1. `'LC101'`
1. `'Capitalized Letters'`
1. `'I love the smell of code in the morning.'`
{{% /notice %}}

## Part Two: Reverse Digits

The `reverseCharacters` function works great on strings, but what if the argument passed to the function is a number? Using `console.log(reverseCharacters(1234));` results in an error, since `split` only works on strings (TRY IT). When passed a number, we want the function to return a number with all the digits reversed (e.g. 1234 converts to 4321 and NOT the string `"4321"`).
1. Add an `if` statement to `reverseCharacters` to check the `typeof` the parameter.
1. If `typeof` is 'string', return the reversed string as before.
1. If `typeof` is 'number', convert the parameter to a string, reverse the characters, then convert it back into a number.
1. Return the reversed number.
1. Be sure to print the result returned by the function to verify that your code works for *both strings and numbers*. Do this before moving on to the next exercise.

{{% notice green Tip "rocket" %}}
Use these samples for testing:

1. `1234`
1. `'LC101'`
1. `8675309`
1. `'radar'`
{{% /notice %}}

## Part Three: Complete Reversal

Now we are ready to finish our complete reversal process. Create a new function with one parameter, which is the array we want to change. The function should:
1. Define and initialize an empty array.
1. Loop through the old array.
1. For each element in the old array, call `reverseCharacters` to flip the characters or digits.
1. Add the reversed string (or number) to the array defined in part 'a'.
1. Return the final, reversed array.
1. *Be sure to print the results from each test case in order to verify your code*.

{{% notice green Tip "rocket" %}}
Use this sample data for testing.

| Input                                     | Output                                |
|-------------------------------------------|---------------------------------------|
| `['apple', 'potato', 'Capitalized Words']` | `['sdroW dezilatipaC', 'otatop', 'elppa']` |
| `[123, 8897, 42, 1138, 8675309]`           | `[9035768, 8311, 24, 7988, 321]`       |
| `['hello', 'world', 123, 'orange']`        | `['egnaro', 321, 'dlrow', 'olleh']`    |
{{% /notice %}}

## Bonus Missions

Define a function with one parameter, which will be a string. The function must do the following:

1. Have a clear, descriptive name like `funPhrase`.
1. Retrieve only the last character from strings with lengths of 3 or less.
1. Retrieve only the first 3 characters from strings with lengths larger than 3.
1. Use a template literal to return the phrase `We put the '___' in '___'.` Fill the first blank with the modified string, and fill the second blank with the original string.

### Test your function:
1. Outside of the function, define the variable `str` and initialize it with a string (e.g. `'Functions rock!'`).
1. Call your function and print the returned phrase.

### The area of a rectangle is equal to its *length x width*.
1. Define a function with the required parameters to calculate the area of a rectangle.
1. The function should *return* the area, NOT print it.
1. Call your area function by passing in two arguments - the length and width.
1. If only one argument is passed to the function, then the shape is a square. Modify your code to deal with this case.
1. Use a template literal to print, "The area is ____ cm^2."

{{% notice green Tip "green" %}}
Use these test cases.

1. length = 2, width = 4 (area = 8)
1. length = 14, width = 7 (area = 98)
1. length = 20 (area = 400)
{{% /notice %}}
