---
title: "Booleans"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 1
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

One of the core features of any programming language is the ability to conditionally execute a segment of code. This means that a program will run a segment of code *only if* a given condition is met.

{{% notice blue Example "rocket" %}}
Consider a banking application that can remind you when a bill is due. The application will notify you that a bill is due soon, but *only if* the bill has not already been paid.
{{% /notice %}}

The condition for the above example is: Send a notification of an upcoming bill only if the statement "the bill is unpaid" is true. In order to state something like this in JavaScript, we need to understand how programming languages represent true and false.

## Boolean Values

The JavaScript data type for storing true and false values is `boolean`, named after the British mathematician George Boole.

{{% notice blue Note "rocket" %}}
George Boole created [Boolean Algebra](https://en.wikipedia.org/wiki/Boolean_algebra), which is the basis of all modern computer arithmetic.
{{% /notice %}}

There are only two **boolean values**---`true` and `false`. JavaScript is case-sensitive, so `True` and `False` are *not* valid boolean values.

{{% notice blue Example "rocket" %}}
```javascript
console.log(true);
console.log(typeof true);
console.log(typeof false);
```

**Console Output**

```
true
boolean
boolean
```
{{% /notice %}}

The values `true` and `false` are *not* strings. If you use quotes to surround booleans (`"true"` and `"false"`), those values become strings.

{{% notice blue Example "rocket" %}}
```javascript
console.log(typeof true);
console.log(typeof "true");
```

**Console Output**

```console
boolean
string
```
{{% /notice %}}

## Boolean Conversion

As with the number and string data types, the boolean type also has a conversion function, `Boolean`. It works similarly to the `Number` and `String` functions, attempting to convert a non-boolean value to a boolean.

{{% notice blue "Try it" "rocket" %}}
Explore how `Boolean` converts various non-boolean values.

```javascript
console.log(Boolean("true"));
console.log(Boolean("TRUE"));
console.log(Boolean(0));
console.log(Boolean(1));
console.log(Boolean(''));
console.log(Boolean('LaunchCode'));
```
{{% /notice %}}

## Boolean Expressions

A **boolean expression** is an expression that evaluates to either `true` or `false`. The equality operator, `==`, compares two values and returns true or false depending on whether the values are equal.

{{% notice blue Example "rocket" %}}
```javascript
console.log(5 == 5);
console.log(5 == 6);
```

**Console Output**

```console
true
false
```
{{% /notice %}}

In the first statement, the two operands are equal, so the expression evaluates to `true`. In the second statement, 5 is not equal to 6, so we get `false`.

We can also use `==` to see that `true` and `"true"` are not equal.

{{% notice blue Example "rocket" %}}
```javascript
console.log(true == "true");
```

**Console Output**

```console
false
```
{{% /notice %}}

### Comparison Operators

The `==` operator is one of six common **comparison operators**.

{{% notice blue "Comparison Operators Examples" "rocket" %}}
| Operator | Description | Examples Returning `true` | Examples Returning `false` |
|----------|-------------|---------------------------|----------------------------|
| Equal (`==`) | Returns `true` if the two operands are equal, and `false` otherwise. | `7 == 7` `"dog" == "dog"` | `7 == 5` `"dog" == "cat"` |
| Not equal (`!=`) | Returns `true` if the two operands are not equal, and `false` otherwise. | `7 != 5` `"dog" != "cat"` | `7 != 7` `"dog" != "dog"`|
| Greater than (`>`)  | Returns `true` if the left-hand operand is greater than the right-hand operand, and `false` otherwise. | `7 > 5` and `'b' > 'a'` | `5 > 7` and `'a' > 'b'` |
| Less than (`<`)     | Returns `true` if the left-hand operand is less than the right-hand operand, and `false` otherwise. | `5 < 7` and `'a' < 'b'` | `7 < 5` and `'b' < 'a'` |
| Greater than or equal (`>=`) | Returns `true` if the left-hand operand is greater than or equal to the right-hand operand, and `false` otherwise. | `7 >= 5`, `7 >= 7`, `'b' >= 'a'`, and `'b' >= 'b'` | `5 >= 7` `'a' >= 'b'` |
| Less than or equal (`<=`) | Returns `true` if the left-hand operand is less than or equal to the right-hand operand, and `false` otherwise. | `5 <= 7`, `5 <= 5`, `'a' <= 'b'`, and `'a' <= 'a'` | `7 <= 5` and `'b' <= 'a'` |
{{% /notice %}}

Although these operations are probably familiar, the JavaScript symbols are different from the mathematical symbols. A common error is to use a single equal sign (`=`) instead of a double equal sign (`==`). Remember that `=` is an *assignment* operator and `==` is a *comparison* operator. Also note that `=<` and `=>` are not recognized operators.

An equality test is *symmetric*, meaning that we can swap the places of the operands and the result is the same. For a variable `a`, if `a == 7` is `true` then `7 == a` is also `true`. However, an assignment statement is not symmetric: `a = 7` is legal while `7 = a` is not.

{{% notice red Warning "rocket" %}}
If you explore the equality operator in more depth, you will find some surprises. For example, the following comparisons return `true`:

- `7 == "7"`
- `0 == false`
- `0 == ''`

We will explore the nuances of `==` in the upcoming section [equality](#equality), and introduce two new operators, `===` and `!==`, that will align more closely with our intuitive notion of equality.
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Under which conditions does `Boolean` convert a string to `true`?

1. Only when the string is `"true"`.
1. Whenever the string contains any non-whitespace character.
1. Whenever the string is non-empty.
1. Never. It converts all strings to `false`.

<!-- Solution: Whener the string is non-empty -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
Which of the following is a Boolean expression? Select all that apply.

a. `3 == 4`
b. `3 + 4`
c. `3 + 4 === 7`
d. `"false"`

<!-- Solution: 3 == 4 and 3 +4 === 7 -->
{{% /notice %}}