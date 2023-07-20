# String Methods

JavaScript provides many useful methods for string objects. Recall that
a method is a function that \"belongs to\" a specific object. Methods
will typically result in some operation being carried out on the data
within an object. For strings, this means that our methods will
typically transform the characters of the given string in some way.

As we have learned, strings are immutable. Therefore, string methods
will not change the value of a string itself, but instead will *return*
a new string that is the result of the given operation.

We saw this behavior in the `toLowerCase` example.

::: admonition
Example

``` {.js linenos=""}
let nonprofit = "LaunchCode";

console.log(nonprofit.toLowerCase());
console.log(nonprofit);
```

**Console Output**

    launchcode
    LaunchCode
:::

While `nonprofit.toLowerCase()` evaluated to `"launchcode"`, the value
of `nonprofit` was left unchanged. This will be case for each of the
string methods.

## Common String Methods

::: index
single: string; methods
:::

Here we present the most commonly-used string methods. You can find
documentation for other string methods at:

-   [W3Schools](https://www.w3schools.com/jsref/jsref_obj_string.asp)
-   [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Methods_2)

  Method                                                                      Syntax                                              Description
  --------------------------------------------------------------------------- --------------------------------------------------- -------------------------------------------------------------------------------------------------------------------------
  `indexOf <string-indexof-examples>`{.interpreted-text role="ref"}           `stringName.indexOf(substr)`                        Returns the index of the first occurrence of the substring in the string, and returns -1 if the substring is not found.
  `toLowerCase <string-tolowercase-examples>`{.interpreted-text role="ref"}   `stringName.toLowerCase()`                          Returns a copy of the given string, with all uppercase letters converted to lowercase.
  `toUpperCase <string-touppercase-examples>`{.interpreted-text role="ref"}   `stringName.toUpperCase()`                          Returns a copy of the given string, with all lowercase letters converted to uppercase.
  `trim <string-trim-examples>`{.interpreted-text role="ref"}                 `stringName.trim()`                                 Returns a copy of the given string with the leading and trailing whitespace removed.
  `replace <string-replace-examples>`{.interpreted-text role="ref"}           `stringName.replace(searchChar, replacementChar)`   Returns a copy of `stringName`, with the first occurrence of `searchChar` replaced by `replacementChar`.
  `slice <string-slice-examples>`{.interpreted-text role="ref"}               `stringName.slice(i, j)`                            Returns the substring consisting of characters from index `i` through index `j-1`.

  : Common String Methods

::: tip
::: title
Tip
:::

String methods can be combined in a process called **method chaining**.
Given `word = 'JavaScript';`, word.toUpperCase() returns `JAVASCRIPT`.
What would `word.slice(4).toUpperCase()` return? [Try it at
repl.it](https://repl.it/@launchcode/Intro-To-Method-Chaining).
:::

## Check Your Understanding

Follow the links in the table above for the `replace`, `slice`, and
`trim` methods. Review the content and then answer the following
questions.

::: admonition
Question

What is printed by the following code?

``` {.js linenos=""}
let language = "JavaScript";
language.replace('J', 'Q');
language.slice(0,5);
console.log(language);
```

1.  `"JavaScript"`
2.  `"QavaScript"`
3.  `"QavaSc"`
4.  `"QavaS"`
:::

::: admonition
Question

Given `language = 'JavaScript';`, what does `language.slice(1,6)`
return?

1.  `"avaScr"`
2.  `"JavaSc"`
3.  `"avaSc"`
4.  `"JavaS"`
:::

::: admonition
Question

What is the value of the string printed by the following program?

``` {.js linenos=""}
let org = "  The LaunchCode Foundation ";
let trimmed = org.trim();

console.log(trimmed);
```

1.  `"  The LaunchCode Foundation "`
2.  `"The LaunchCode Foundation"`
3.  `"TheLaunchCodeFoundation"`
4.  `" The LaunchCode Foundation"`
:::
