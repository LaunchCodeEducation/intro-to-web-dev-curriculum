# Booleans

::: index
data type
:::

One of the core features of any programming language is the ability to
conditionally execute a segment of code. This means that a program will
run a segment of code *only if* a given condition is met.

::: admonition
Example

Consider a banking application that can remind you when a bill is due.
The application will notify you that a bill is due soon, but *only if*
the bill has not already been paid.
:::

The condition for the above example is: Send a notification of an
upcoming bill only if the statement \"the bill is unpaid\" is true. In
order to state something like this in JavaScript, we need to understand
how programming languages represent true and false.

## Boolean Values

::: index
! true, ! false, ! boolean
:::

::: index
single: boolean; value
:::

The JavaScript data type for storing true and false values is `boolean`,
named after the British mathematician George Boole.

::: admonition
Fun Fact

George Boole created [Boolean
Algebra](https://en.wikipedia.org/wiki/Boolean_algebra), which is the
basis of all modern computer arithmetic.
:::

There are only two **boolean values**\-\--`true` and `false`. JavaScript
is case-sensitive, so `True` and `False` are *not* valid boolean values.

::: admonition
Example

``` {.js linenos=""}
console.log(true);
console.log(typeof true);
console.log(typeof false);
```

**Console Output**

    true
    boolean
    boolean
:::

The values `true` and `false` are *not* strings. If you use quotes to
surround booleans (`"true"` and `"false"`), those values become strings.

::: admonition
Example

``` {.js linenos=""}
console.log(typeof true);
console.log(typeof "true");
```

**Console Output**

    boolean
    string
:::

## Boolean Conversion

::: index
! Boolean(), type conversion
:::

As with the number and string data types, the boolean type also has a
conversion function, `Boolean`. It works similarly to the `Number` and
`String` functions, attempting to convert a non-boolean value to a
boolean.

::: admonition
Try It!

Explore how `Boolean` converts various non-boolean values.

::: {.replit linenos="" slug="Boolean-Type-Conversion"}
js

console.log(Boolean(\"true\")); console.log(Boolean(\"TRUE\"));
console.log(Boolean(0)); console.log(Boolean(1));
console.log(Boolean(\'\')); console.log(Boolean(\'LaunchCode\'));
:::
:::

## Boolean Expressions

::: index
single: boolean; expression
:::

::: index
single: operator; equality
:::

::: index
! ==
:::

A **boolean expression** is an expression that evaluates to either
`true` or `false`. The equality operator, `==`, compares two values and
returns true or false depending on whether the values are equal.

::: admonition
Example

``` {.js linenos=""}
console.log(5 == 5);
console.log(5 == 6);
```

**Console Output**

    true
    false
:::

In the first statement, the two operands are equal, so the expression
evaluates to `true`. In the second statement, 5 is not equal to 6, so we
get `false`.

We can also use `==` to see that `true` and `"true"` are not equal.

::: admonition
Example

``` js
console.log(true == "true");
```

**Console Output**

    false
:::

### Comparison Operators

::: index
single: operator; comparison
:::

The `==` operator is one of six common **comparison operators**.

::: index
==, ! !=, ! \<, ! \>, ! \<=, ! \>=
:::

+----------------+----------------+----------------+----------------+
| Operator       | Description    | Examples       | Examples       |
|                |                | Returning      | Returning      |
|                |                | `true`         | `false`        |
+================+================+================+================+
| Equal (`==`)   | Returns `true` | `7 == 7`       | `7 == 5`       |
|                | if the two     |                |                |
|                | operands are   | `"             | `"             |
|                | equal, and     | dog" == "dog"` | dog" == "cat"` |
|                | `false`        |                |                |
|                | otherwise.     |                |                |
+----------------+----------------+----------------+----------------+
| Not            | Returns `true` | `7 != 5`       | `7 != 7`       |
| equal(`!=`)    | if the two     |                |                |
|                | operands are   | `"             | `"             |
|                | not equal, and | dog" != "cat"` | dog" != "dog"` |
|                | `false`        |                |                |
|                | otherwise.     |                |                |
+----------------+----------------+----------------+----------------+
| Greater than   | Returns `true` | `7 > 5`        | `5 > 7`        |
| (`>`)          | if the         |                |                |
|                | left-hand      | `'b' > 'a'`    | `'a' > 'b'`    |
|                | operand is     |                |                |
|                | greater than   |                |                |
|                | the right-hand |                |                |
|                | operand, and   |                |                |
|                | `false`        |                |                |
|                | otherwise.     |                |                |
+----------------+----------------+----------------+----------------+
| Less than      | Returns `true` | `5 < 7`        | `7 < 5`        |
| (`<`)          | if the         |                |                |
|                | left-hand      | `'a' < 'b'`    | `'b' < 'a'`    |
|                | operand is     |                |                |
|                | less than the  |                |                |
|                | right-hand     |                |                |
|                | operand, and   |                |                |
|                | `false`        |                |                |
|                | otherwise.     |                |                |
+----------------+----------------+----------------+----------------+
| Greater than   | Returns `true` | `7 >= 5`       | `5 >= 7`       |
| or equal       | if the         |                |                |
| (`>=`)         | left-hand      | `7 >= 7`       | `'a' >= 'b'`   |
|                | operand is     |                |                |
|                | greater than   | `'b' >= 'a'`   |                |
|                | or equal to    |                |                |
|                | the right-hand | `'b' >= 'b'`   |                |
|                | operand, and   |                |                |
|                | `false`        |                |                |
|                | otherwise.     |                |                |
+----------------+----------------+----------------+----------------+
| Less than or   | Returns `true` | `5 <= 7`       | `7 <= 5`       |
| equal (`<=`)   | if the         |                |                |
|                | left-hand      | `5 <= 5`       | `'b' <= 'a'`   |
|                | operand is     |                |                |
|                | less than or   | `'a' <= 'b'`   |                |
|                | equal to the   |                |                |
|                | right-hand     | `'a' <= 'a'`   |                |
|                | operand, and   |                |                |
|                | `false`        |                |                |
|                | otherwise.     |                |                |
+----------------+----------------+----------------+----------------+

: Comparison Operators

Although these operations are probably familiar, the JavaScript symbols
are different from the mathematical symbols. A common error is to use a
single equal sign (`=`) instead of a double equal sign (`==`). Remember
that `=` is an *assignment* operator and `==` is a *comparison*
operator. Also note that `=<` and `=>` are not recognized operators.

An equality test is *symmetric*, meaning that we can swap the places of
the operands and the result is the same. For a variable `a`, if `a == 7`
is `true` then `7 == a` is also `true`. However, an assignment statement
is not symmetric: `a = 7` is legal while `7 = a` is not.

::: admonition
Warning

If you explore the equality operator in more depth, you will find some
surprises. For example, the following comparisons return `true`:

-   `7 == "7"`
-   `0 == false`
-   `0 == ''`

We will explore the nuances of `==` in the upcoming section
`equality`{.interpreted-text role="ref"}, and introduce two new
operators, `===` and `!==`, that will align more closely with our
intuitive notion of equality.
:::

## Check Your Understanding

::: admonition
Question

Under which conditions does `Boolean` convert a string to `true`?

1.  Only when the string is `"true"`.
2.  Whenever the string contains any non-whitespace character.
3.  Whenever the string is non-empty.
4.  Never. It converts all strings to `false`.
:::

::: admonition
Question

Which of the following is a Boolean expression? Select all that apply.

1.  `3 == 4`
2.  `3 + 4`
3.  `3 + 4 === 7`
4.  `"false"`
:::
