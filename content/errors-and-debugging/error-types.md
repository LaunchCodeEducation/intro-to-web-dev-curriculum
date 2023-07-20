# Error Types

::: index
single: error; syntax single: error; type single: error; runtime single:
object; built-in
:::

An **error type** is the classification that JavaScript uses to group
errors based on their cause. In future lessons, we will learn that an
error type is actually something called a **built-in object**. For now,
understanding the different types of errors will help us become faster
at debugging.

Each error that JavaScript reports has an error type, and the type is
included in the error message. For example,
`an earlier message <syntax-error>`{.interpreted-text role="ref"}
reported the error type as `SyntaxError`.

    /Users/chris/dev/sandbox/js/syntax.js:2
    console.log("Hello, name);
                ^^^^^^^^^^^^^^

    SyntaxError: Invalid or unexpected token
       at new Script (vm.js:85:7)
       at createScript (vm.js:266:10)
       at Object.runInThisContext (vm.js:314:10)
       at Module._compile (internal/modules/cjs/loader.js:698:28)
       at Object.Module._extensions..js (internal/modules/cjs/loader.js:749:10)
       at Module.load (internal/modules/cjs/loader.js:630:32)
       at tryModuleLoad (internal/modules/cjs/loader.js:570:12)
       at Function.Module._load (internal/modules/cjs/loader.js:562:3)
       at Function.Module.runMain (internal/modules/cjs/loader.js:801:12)
       at internal/main/run_main_module.js:21:11

We have now seen two error types, `ReferenceError` and `SyntaxError`.
There are several other [error types in
JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects#Fundamental_objects),
such as `TypeError` and `RangeError`.

The following table describes all JavaScript error types. Some of these
relate to coding concepts we have not covered yet, but we include them
here as a reference for future use.

+----------------+----------------+----------------+----------------+
| Error Type     | Description    | Example of     | Example        |
|                |                | code           | description    |
|                |                | triggering the |                |
|                |                | error          |                |
+================+================+================+================+
| `SyntaxError`  | Occurs when    | ..             | The call to    |
|                | trying to      | sourcecode::   | `console.log`  |
|                | parse          | js             | does not have  |
|                | syntactically  |                | a required     |
|                | invalid code.  | > console.     | close          |
|                |                | log(\"hello\"; | parenthesis.   |
+----------------+----------------+----------------+----------------+
| `R             | Occurs when a  | ..             | The variable   |
| eferenceError` | non-existent   | sourcecode::   | `firstname`    |
|                | variable is    | js :linenos:   | does not       |
|                | us             |                | exist; it is a |
|                | ed/referenced. | > let          | misspelling of |
|                |                | > firstName =  | `firstName`.   |
|                |                | > \"Jack\";    |                |
|                |                | > console.l    |                |
|                |                | og(firstname); |                |
+----------------+----------------+----------------+----------------+
| `TypeError`    | Occurs when    | ..             | The numeric    |
|                | trying to use  | sourcecode::   | value `1` is   |
|                | a value in an  | js             | not a          |
|                | invalid way.   |                | function, so   |
|                |                | > 1();         | trying to use  |
|                |                |                | it as one      |
|                |                |                | results in     |
|                |                |                | `Type          |
|                |                |                | Error: 1 is no |
|                |                |                | t a function`. |
+----------------+----------------+----------------+----------------+
| `RangeError`   | Occurs when    | ..             | The            |
|                | passing an     | sourcecode::   | constructor    |
|                | invalid value  | js             | function       |
|                | to a function. |                | `Array(n)`     |
|                |                | > let nums =   | creates an     |
|                |                | > Array(-1);   | empty array of |
|                |                |                | length `n`. It |
|                |                |                | is not         |
|                |                |                | possible to    |
|                |                |                | create an      |
|                |                |                | array with     |
|                |                |                | negative       |
|                |                |                | length, so the |
|                |                |                | code results   |
|                |                |                | in             |
|                |                |                | `RangeE        |
|                |                |                | rror: Invalid  |
|                |                |                | array length`. |
+----------------+----------------+----------------+----------------+
| `URIError`     | Occurs when    | ..             | The `%`        |
|                | improperly     | sourcecode::   | character is   |
|                | using a global | js             | used to encode |
|                | URI-handling   |                | characters not |
|                | function.      | > dec          | otherwise      |
|                | (\'URI\' =     | odeURI(\'%\'); | allowed in     |
|                | Uniform        |                | URIs, such as  |
|                | Resource       |                | spaces         |
|                | Identifier)    |                | (`%20`). If an |
|                |                |                | invalid        |
|                |                |                | character      |
|                |                |                | encoding is    |
|                |                |                | given, a       |
|                |                |                | `URIError`     |
|                |                |                | results.       |
+----------------+----------------+----------------+----------------+
| `Error`        | The type from  | ..             | Manually       |
|                | which all      | sourcecode::   | triggers an    |
|                | other errors   | js             | error with the |
|                | are built. It  |                | given message. |
|                | can be used to | > throw        |                |
|                | generate       | > Err          |                |
|                | progra         | or(\"Something |                |
|                | mmer-triggered | > bad          |                |
|                | and            | >              |                |
|                | prog           |  happened!\"); |                |
|                | rammer-defined |                |                |
|                | errors.        |                |                |
+----------------+----------------+----------------+----------------+

: JavaScript Error Types

Each time you encounter a new error type, take the time to understand
what it is, and what JavaScript is trying to tell you. Remember, **error
messages are your friends!**
