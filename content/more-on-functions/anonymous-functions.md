# Anonymous Functions

::: index
single: function, named single: function, anonymous
:::

You already know
`one method for creating a function <function-syntax>`{.interpreted-text
role="ref"}:

``` {.js linenos=""}
function myFunction(parameter1, parameter2,..., parameterN) {

   // function body

}
```

A function defined in this way is a **named function** (`myFunction`, in
the example above).

Many programming languages, including JavaScript, allow us to create
**anonymous functions**, which *do not* have names. We can create an
anonymous function by simply leaving off the function name when defining
it:

``` {.js linenos=""}
function (parameter1, parameter2,..., parameterN) {

   // function body

}
```

You might be asking yourself, *How do I call a function if it doesn\'t
have a name?!* Good question. Let\'s address that now.

## Anonymous Function Variables

Anonymous functions are often assigned to variables when they are
created, which allows them to be called using the variable\'s name.

::: admonition
Example

Let\'s create and use a simple anonymous function that returns the sum
of two numbers.

``` {.js linenos=""}
let add = function(a, b) {
   return a + b;
};

console.log(add(1, 1));
```

**Console Output**

    2
:::

The variable `add` refers to the anonymous function created on lines 1
through 3. We call the function using the *variable* name, since the
function doesn\'t have a name.

The visual analogy here is the same as that of a variable referring to a
named function.

<figure>
<img src="figures/function-var-anonymous.png"
alt="figures/function-var-anonymous.png" />
<figcaption>A variable that refers to an anonymous
function.</figcaption>
</figure>

::: warning
::: title
Warning
:::

Like other variable declarations, an assignment statement using an
anonymous function should be terminated by a semi-colon, `;`. This is
easy to overlook, since named functions do *not* end with a semi-colon.
:::

## Check Your Understanding

::: admonition
Question

Convert the following named function to an anonymous function that is
stored in a variable.

::: {.replit linenos="" slug="Refactor-to-make-anonymous"}
js

function reverse(str) {

:   let lettersArray = str.split(\'\'); let reversedLettersArray =
    lettersArray.reverse(); return reversedLettersArray.join(\'\');

}
:::
:::

::: admonition
Question

Consider the code sample below, which declares an anonymous function
beginning on line 1.

``` {.js linenos=""}
let f1 = function(str) {
   return str + str;
};

let f2 = f1;
```

Which of the following are valid ways of invoking the anonymous function
with the argument `"abcd"`? (Choose all that apply.)

1.  `f1("abcd");`
2.  `function("abcd");`
3.  `f2("abcd");`
4.  It is not possible to invoke the anonymous function, since it
    doesn't have a name.
:::

::: admonition
Question

Complete the following code snippet so that it logs an error message if
`userInput` is negative.

::: {.replit linenos="" slug="Check-Fill-in-the-Code"}
js

let logger = function(errorMsg) {

:   console.log(\"ERROR: \" + errorMsg);

};

if (userInput \< 0) {

:   \_\_\_\_\_\_\_\_\_\_\_\_(\"Invalid input\");

}
:::
:::
