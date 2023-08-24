---
title: "Nested Conditionals"
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

We can write code with more complex branching behavior by combining conditionals and, in particular, by nesting conditionals. Let's see how this works by tackling the following problem.

{{% notice blue Example "rocket" %}}
Write code that prints different messages based on the value of a number variable. If the number is odd, print nothing. If it is even, print "EVEN". If it is also positive print "POSITIVE".
{{% /notice %}}

Our first attempt at a solution might look like this:

```javascript
let num = 7;

if (num % 2 === 0) {
   console.log("EVEN");
}

if (num > 0) {
   console.log("POSITIVE");
}
```

**Console Output**

```console
POSITIVE
```

We find that the output is `POSITIVE`, even though 7 is odd and so nothing should be printed. This code doesn't work as desired because we only want to test for positivity when we already know that the number is even. We can enable this behavior by putting the second conditional *inside* the first.

```javascript
let num = 7;

if (num % 2 === 0) {
    console.log("EVEN");

    if (num > 0) {
        console.log("POSITIVE");
    }
}
```

{{% notice blue "Try it!" "rocket" %}}
Run the previous example with several different values for `num` (even, odd, positive, negative) to ensure it works as desired. Nice, huh?
{{% /notice %}}

Notice that when we put one conditional inside another, the body of the nested conditional is indented by two tabs rather than one. This convention provides an easy, visual way to determine which code is part of which conditional.

## Check Your Understanding

{{% notice green Question "rocket" %}}
What is printed when the following code runs?

```javascript
let num = 7;

if (num % 2 === 0) {
    if (num % 2 === 1) {
        console.log("odd");
    }
}
```

1. The code won't run due to invalid syntax.
2. `odd`
3. `even`
4. The code runs but doesn't print anything

<!-- Solution: The code runs but doesn't print anything -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
Considering the same conditional used in the previous question, which values of `num` would result in `"odd"` being printed?

```javascript
if (num % 2 === 0) {
    if (num % 2 === 1) {
        console.log("odd");
    }
}
```

1. Even values of `num`.
2. Odd values of `num`.
3. No values. It is impossible for the call to `console.log` to ever run, given the two conditions.
4. `num` is 0.

<!-- Solution: No values. -->
{{% /notice %}}