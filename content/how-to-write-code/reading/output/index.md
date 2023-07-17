---
title: "Output with console.log"
date: 2023-07-13T14:00:03-05:00
draft: false
weight: 4
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

<!-- TODO: Add link to Chapter 2 -->

In the Hello World section, you experimented with
displaying text on the screen. Technically, you sent the words to the
**console**, which is a simple window where the user can type commands or view
output. We used a print function without explicitly talking about how it works.
Let’s fix that now.

We *call* the print function using the syntax `console.log()`. When the code
runs, we want it to tell the computer, *Please display what is inside the () on
the screen*. For us, the words are enough - we want to LOG the text to the
CONSOLE. However, the computer only understands binary or hexadecimal
instructions. We need the compiler to change the keywords *console* and *log*
into a format that the machine understands.

## Examples

Open the `ConsoleLogExamples01` file in `how-to-write-code`. Run the code with `node consolelogexamples01` and note the difference between the
outputs:

```js {linenos=table}
   console.log('Hello, JavaScript.');
   console.log(2001);
   console.log("What","do","commas","do?");
   console.log("Does", "adding",      "space", "matter?");
   console.log('Launch' + 'Code');
   console.log("LaunchCode was founded in", 2013);
```

Observations line by line:

1. In the line 1, we print some text, which is surrounded by quotes.
1. In the line 2, we print a number. Note the absence of quote marks.
1. In line 3, we use four words, separated by commas, all within the same
   set of parentheses `()`. When these four words print, they show up on
   the same line but separated by spaces.
1. The code in line 4 puts extra spaces after the commas. How does this affect
   the output?
1. Line 5 also prints more words, but in this case the code uses `+`
   instead of a comma. The result is to print the words without spaces in
   between.
1. Line 6 prints text and a number with a space in between.

## Two Special Characters

One final observation for all of the examples above is that each time we use
`console.log`, a **newline** is inserted after the printed content. Think of
a newline as the same as hitting the Enter or Return key on your keyboard. The
cursor moves to the beginning of the next line.

For the computer, *newline* is an invisible character that is used to tell the
machine to move to the next line. It is possible to use this invisible
character with the special representation `\n`.

{{% notice blue "Example" "rocket" %}}

   Experiment with the newline character by opening up `ConsoleLogExamples02` and running the code.

   ```js {linenos=table}
      console.log("Some Programming Languages:");

      console.log("Python\nJavaScript\nJava\nC#\nSwift");
   ```

{{% /notice %}}

In addition to the newline character, there is also a special tab character,
`\t`. Go back to the eight examples above and experiment with using `\t`
and `\n`.