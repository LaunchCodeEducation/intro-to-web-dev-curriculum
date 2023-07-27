---
title: "Conditionals"
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

At the beginning of this chapter, we decided that we wanted to be able to write code that only executes when a given condition is true.

Again, here is our motivating example:

{{% notice blue Example "rocket" %}}
Consider a banking application that can remind you when a bill is due. The application will notify you that a bill is due soon, but *only if* the bill has not already been paid.
{{% /notice %}}

We summarized the condition as follows: Send a notification of an upcoming bill if the statement "the bill is unpaid" is true.

In such a program, JavaScript uses booleans to represent the conditional "the bill is unpaid". Based on the truth of this statement, the program executes or skips the code for notifying the user.

The JavaScript construct that enables such behavior is a **conditional**.

## `if` Statements

The most basic form of a conditional is an **if statement**. Here's how to create one in JavaScript:

![The structure of a conditional with an if statement](pictures/if.png?classes=border)

Let's look at each component of this new syntax.

- The `if` statement consists of a header line and a body. The header line begins with the keyword `if` followed by a boolean expression enclosed in parentheses.
- `condition` is a boolean expression (an expression that evaluates to either true or false).
- The statements that follow the condition, within `{}`, make up a **code block**. The code within the brackets `{}` will be executed if the condition evaluates to true. If the condition evaluates to false, the code within the brackets is ignored.

Here is an explicit example that mimics our banking program.

{{% notice blue Example "rocket" %}}
```javascript
let billHasBeenPaid = false;

if (!billHasBeenPaid) {
   console.log("Your bill is due soon!");
}
```

**Console Output**

```console
Your bill is due soon!
```
{{% /notice %}}

The message prints because `billHasBeenPaid` is `false`, so `!billHasBeenPaid` evaluates to `true`. If we were to change the value of `billHasBeenPaid` to be `true`, then `!billHasBeenPaid` would evaluate to `false` and the code block would not execute.

The condition in an `if` statement can be any boolean expression, such as `name === 'Jack'` or `points > 10` (here, `name` and `points` are variables). Additionally, the code block associated with a conditional can be of any size. This conditional has a code block with two lines of code:

{{% notice blue Example "rocket" %}}
```javascript
if (num % 2 === 0 && num > 3) {
   console.log(num, "is even");
   console.log(num, "is greater than 3");
}
```
{{% /notice %}}

While not required, the code within a conditional code block is typically indented to make it more readable. Similarly, it is a common convention to place the opening `{` at the end of the first line, and the closing `}` on a line of its own following the last line of the code block.

You should follow such conventions, even though ignoring them will not create an error. To see why, compare the readability of this example, which is functionally equivalent to the one above.

```javascript
if (num % 2 === 0 && num > 3)
{ console.log(num, "is even");
 console.log(num, "is greater than 3"); }
```

Aside from being more aesthetically pleasing, the first version also makes it
easier to visually identify the pair of matching curly brackets, which helps
prevent syntax errors.

{{% notice orange Warning "rocket" %}}
If the code block associated with a conditional consists of only one
line, then the enclosing curly brackets can be omitted.

However, this is NOT a best-practice, as it makes the logic harder to
follow.

```javascript
if (!billHasBeenPaid)
   console.log("Your bill is due soon!");
```

We will use curly brackets for ALL conditional code blocks, and encourage
you to do so as well, at least until you become comfortable with reading and
writing more complex JavaScript.
{{% /notice %}}

## `else` Clauses

An **else clause** can be paired with an `if` statement to specify code that should be executed when the condition is false.

![A conditional with an else clause](pictures/if-else.png?classes=border)

We can use an `else` clause within our bank app to send a message if no bills are currently due.

{{% notice blue Example "rocket" %}}
```javascript
let billHasBeenPaid = true;

if (!billHasBeenPaid) {
   console.log("Your bill is due soon!");
} else {
   console.log("Your payments are up to date.");
}
```

**Console Output**

```console
Your payments are up to date.
```
{{% /notice %}}

This structure is known as an **if-else statement**, and it provides a
mechanism for **branching**. The flow of the program can take one of two paths
when it reaches a conditional, depending on whether the condition is `true`
or `false`.

![A diagram showing how the flow of a program branches based on the value of the condition in an if-else statement. If the condition is true, one code block executes. If the condition is false, a different code block executes.](pictures/conditional-flow.png?classes=border)

## `else if` Statements

If-else statements allow us to construct two alternative paths. A single condition determines which path will be followed. We can build more complex conditionals using an `else if` clause. These allow us to add additional conditions and code blocks, which facilitate more complex branching.

{{% notice blue Example "rocket" %}}
```javascript
let x = 10;
let y = 20;

if (x > y) {
   console.log("x is greater than y");
} else if (x < y) {
   console.log("x is less than y");
} else {
   console.log("x and y are equal");
}
```

**Console Output**

```console
x is less than y
```
{{% /notice %}}

Let's summarize the flow of execution of this conditional:

1. Line 4 begins the conditional. The boolean expression `x > y` evaluates to false, since 10 is not greater than 20. This causes line 5 to be skipped.
1. Line 6 contains an else-if statement. The boolean expression `x < y` evaluates to true, since 10 is less than 20. This triggers the execution of line 7.
1. The code block associated with the `else` clause on lines 8-10 is skipped because one of the conditions above was true.

As with a simple `if` statement, the `else` clause is optional in this context as well. The following example does not print anything, since both conditions evaluate to false and there is no `else` clause.

```javascript
let x = 10;
let y = 10;

if (x > y) {
   console.log("x is greater than y");
} else if (x < y) {
   console.log("x is less than y");
}
```

We can construct conditionals using `if`, `else if`, and `else` with a lot of flexibility. The only rules are:

1. We may not use `else` or `else if` without a preceding `if` statement.
2. `else` and `else if` clauses are optional.
3. Multiple `else if` statements may follow the `if` statement, but they must precede the `else` clause, if one is present.
4. Only one `else` clause may be used.

Regardless of the complexity of a conditional, no more than one of the code blocks will be executed.

{{% notice blue Example "rocket" %}}
```javascript
let x = 10;
let y = 20;

if (x > y) {
   console.log("x is greater than y");
} else if (x < y) {
   console.log("x is less than y");
} else if (x % 5 === 0) {
   console.log("x is divisible by 5");
} else if (x % 2 === 0) {
   console.log("x is even");
}
```

**Console Output**

```console
x is less than y
```
{{% /notice %}}

Even though both of the conditions `x % 5 === 0` and `x % 2 === 0` evaluate to `true`, neither of the associated code blocks is executed. When a condition is satisfied, the rest of the conditional is skipped.

## Check Your Understanding

{{% notice green Question "rocket" %}}
What does the following code print?

```javascript
let a = 7;
if (a % 2 === 1) {
   console.log("Launch");
} else if (a > 5) {
   console.log("Code");
} else {
   console.log("LaunchCode");
}
```

1. `"Launch"`
2. `"Code"`
3. `"Launch"` ` "Code"`
4. `"LaunchCode"`

<!-- Solution: Launch -->
{{% /notice %}}