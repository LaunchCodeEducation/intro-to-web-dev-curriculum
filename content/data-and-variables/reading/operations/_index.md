---
title: "Operations"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 6
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## Operators and Operands

Now that we can store data in variables, let's explore how we can generate new data from existing data.

An **operator** is one or more characters that represents a computation like addition, multiplication, or division. The values an operator works on are called **operands**.

The following are all legal JavaScript expressions whose meaning is more or less clear:

- `20 + 32`
- `hour - 1`
- `hour * 60 + minute`
- `minute / 60`
- `5 ** 2`
- `(5 + 9) * (15 - 7)`

For example, in the calculation `20 + 32`, the operator is `+` and the operands are `20` and `32`.

The symbols `+` and `-`, and the use of parentheses for grouping, mean in JavaScript what they mean in mathematics. The asterisk (`*`) is the symbol for multiplication, and `**` is the symbol for exponentiation. Addition, subtraction, multiplication, and exponentiation all do what you expect.

{{% notice blue Example "rocket" %}}
```javascript
console.log(2 + 3);
console.log(2 - 3);
console.log(2 * 3);
console.log(2 ** 3);
console.log(3 ** 2);
```

**Console Output**

```bash
5
-1
6
8
9
```
{{% /notice %}}

We use the same terminology as before, stating that `2 + 3` **returns** the value `5`.

When a variable name appears in the place of an operand, it is replaced with the value that it refers to before the operation is performed. For example, suppose that we wanted to convert 645 minutes into hours. Division is denoted by the operator `/`.

{{% notice blue Example "rocket" %}}
```javascript
let minutes = 645;
let hours = minutes / 60;
console.log(hours);
```

**Console Output**

```bash
10.75
```
{{% /notice %}}

In summary, operators and operands can be combined to create expressions that are evaluated upon execution. Let's discuss some specific types of operators

## Arithmetic Operators

Some of most commonly-used operators are the **arithmetic operators**, which carry out basic mathematical operations. These behave exactly as you are used to, though the modulus operator (`%`) may be new to you.

| Operator | Description | Example |
|----------|-------------|---------|
| Addition (`+`) | Adds the two operands | `2 + 3` returns `5` |
| Subtraction (`-`) | Subtracts the two operands | `2 - 3` returns `-1` |
| Multiplication (`*`)| Multiplies the two operands | `2 * 3` returns `6` |
| Division (`/`) | Divides the first operand by the second | `6 / 2` returns `3` |
| Modulus (`%`) | Aka the remainder operator. Returns the integer remainder of dividing the two operands | `7 % 5` returns `2` |
| Exponentiation (`**`) | Calculates the base (first operand) to the exponent (second operand) power, that is, base<sup>exponent</sup> | `3 ** 2` returns `9`<br>`5 ** -1` returns `0.2` |
| Increment (`++`)   | Adds one to its operand. If used before the operand (`++x`), returns the value of its operand after adding one; if used after the operand (`x++`), returns the value of its operand before adding one | If `x` is `2`, then `++x` sets `x` to `3` and returns `3`, whereas `x++` returns `2` and, only then, sets `x` to `3` |
| Decrement (`--`)   | Subtracts one from its operand. The return value is analogous to that for the increment operator | If `x` is `2`, then `--x` sets `x` to `1` and returns `1`, whereas `x--` returns `2` and, only then, sets `x` to `1` |

While the **modulus operator** (`%`) is common in programming, it is not used much
outside of programming. Let's explore how it works with a few examples.

The `%` operator returns the *remainder* obtained by carrying out integer division of the first operand by the second operand. Therefore, `5 % 3` is `2` because 3 goes into 5 one whole time, with a remainder of 2 left over.

{{% notice blue Examples "rocket" %}}
- 12 % 4 is 0, because 4 divides 12 evenly (that is, there is no remainder)
- 13 % 7 is 6
- 6 % 2 is 0
- 7 % 2 is 1
{{% /notice %}}

The last two examples illustrate a general rule: An integer x is even exactly when `x % 2` is `0` and is odd exactly when `x % 2` is `1`.

{{% notice blue Note "rocket" %}}
The value returned by `a % b` will be in the range from `0` to `b`
   (not including `b`).
{{% /notice %}}

{{% notice green Tip "rocket" %}}
If remainders and the modulus operator seem tricky to you, we recommend getting additional practice at [Khan Academy](https://www.khanacademy.org/computing/computer-science/cryptography/modarithmetic/a/what-is-modular-arithmetic).
{{% /notice %}}

## Order of Operations

When more than one operator appears in an expression, the order of evaluation depends on the **rules of precedence**. JavaScript follows the same precedence rules for its arithmetic operators that mathematics does.

1. Parentheses have the highest precedence and can be used to force an expression to evaluate in the order you want. Since expressions in
parentheses are evaluated first, `2 * (3 - 1)` is 4, and `(1 + 1) ** (5 - 2)` is 8. You can also use parentheses to make an expression easier to read, as in `(minute * 100) / 60`, even though it doesn't change the result.
1. Exponentiation has the next highest precedence, so `2 ** 1 + 1` is 3 and not 4, and `3 * 1 ** 3` is 3 and not 27. Can you explain why?
1. Multiplication, division, and modulus operators have the same precedence, which is higher than addition and subtraction, which also have the same precedence. So `2 * 3 - 1` yields 5 rather than 4, and `5 - 2 * 2` is 1,
not 6.
1. Operators with the *same* precedence are evaluated from left-to-right. So in the expression `6 - 3 + 2`, the subtraction happens first, yielding 3. We then add 2 to get the result 5. If the operations had been evaluated from right to left, the result would have been `6 - (3 + 2)`, which is 1.

{{% notice green Tip "rocket" %}}
The acronym PEMDAS can be used to remember order of operations:

**P** = parentheses

**E** = exponentiation

**M** = multiplication

**D** = division

**A** = addition

**S** = subtraction
{{% /notice %}}

{{% notice blue Note "rocket" %}}
Due to an historical quirk, an exception to the left-to-right rule is the exponentiation operator ``**``. A useful hint is to always use parentheses to force exactly the order you want when exponentiation is involved:

```javascript
// the right-most ** operator is applied first
console.log(2 ** 3 ** 2)
```

```javascript
// use parentheses to force the order you want
console.log((2 ** 3) ** 2)
```

**Console Output**

```bash
512
64
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
What is the value of the following expression?

```javascript
16 - 2 * 5 / 3 + 1
```

1. 14
1. 24
1. 3
1. 13.666666666666666
{{% /notice %}}

{{% notice green Question "rocket" %}}
What is the output of the code below?

```javascript
console.log(1 + 5 % 3);
```
{{% /notice %}}

{{% notice green Question "rocket" %}}
What is the value of the following expression?

```javascript
2 ** 2 ** 3 * 3
```

1. 768
1. 128
1. 12
1. 256
{{% /notice %}}