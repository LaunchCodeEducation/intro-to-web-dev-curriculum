---
title: "String Methods"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 5
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

JavaScript provides many useful methods for string objects. Recall that a method is a function that "belongs to" a specific object. Methods will typically result in some operation being carried out on the data within an object. For strings, this means that our methods will typically transform the characters of the given string in some way.

As we have learned, strings are immutable. Therefore, string methods will not change the value of a string itself, but instead will *return* a new string that is the result of the given operation.

We saw this behavior in the `toLowerCase` example.

{{% notice blue Example "rocket" %}}
```javascript
let nonprofit = "LaunchCode";

console.log(nonprofit.toLowerCase());
console.log(nonprofit);
```

**Console Output**

```console
launchcode
LaunchCode
```
{{% /notice %}}

While `nonprofit.toLowerCase()` evaluated to `"launchcode"`, the value of `nonprofit` was left unchanged. This will be case for each of the string methods.

## Common String Methods

Here we present the most commonly-used string methods. You can find documentation for other string methods at:

- [W3Schools](https://www.w3schools.com/jsref/jsref_obj_string.asp)
- [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Methods_2)

| Method                                      | Syntax                                  | Description                                                                                   |
|---------------------------------------------|-----------------------------------------|-----------------------------------------------------------------------------------------------|
| [indexOf](string-indexof-examples)          | `stringName.indexOf(substr)`           | Returns the index of the first occurrence of the substring in the string, and returns -1 if the substring is not found.                                    |
| [toLowerCase](string-tolowercase-examples)  | `stringName.toLowerCase()`             | Returns a copy of the given string, with all uppercase letters converted to lowercase.       |
| [toUpperCase](string-touppercase-examples)  | `stringName.toUpperCase()`             | Returns a copy of the given string, with all lowercase letters converted to uppercase.       |
| [trim](string-trim-examples)                | `stringName.trim()`                    | Returns a copy of the given string with the leading and trailing whitespace removed.         |
| [replace](string-replace-examples)          | `stringName.replace(searchChar, replacementChar)` | Returns a copy of `stringName`, with the first occurrence of `searchChar` replaced by `replacementChar`. |
| [slice](string-slice-examples)              | `stringName.slice(i, j)`               | Returns the substring consisting of characters from index `i` through index `j-1`.           |

{{% notice green Tip "rocket" %}}
String methods can be combined in a process called **method chaining**. Given `word = 'JavaScript';`, word.toUpperCase() returns `JAVASCRIPT`. What would `word.slice(4).toUpperCase()` return?.
{{% /notice %}}

## Check Your Understanding

Follow the links in the table above for the `replace`, `slice`, and `trim` methods. Review the content and then answer the following questions.

{{% notice green Question "rocket" %}}
What is printed by the following code?

```javascript
let language = "JavaScript";
language.replace('J', 'Q');
language.slice(0,5);
console.log(language);
```

1. `"JavaScript"`
1. `"QavaScript"`
1. `"QavaSc"`
1. `"QavaS"`

<!-- Solution: JavaScript -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
Given `language = 'JavaScript';`, what does `language.slice(1,6)` return?

1. ``"avaScr"``
1. ``"JavaSc"``
1. ``"avaSc"``
1. ``"JavaS"``

<!-- Solution: avaSc -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
What is the value of the string printed by the following program?

```javascript
let org = "  The LaunchCode Foundation ";
let trimmed = org.trim();

console.log(trimmed);
```

1. `"  The LaunchCode Foundation "`
1. `"The LaunchCode Foundation"`
1. `"TheLaunchCodeFoundation"`
1. `" The LaunchCode Foundation"`

<!-- Solution: The LaunchCode Foundation -->
{{% /notice %}}