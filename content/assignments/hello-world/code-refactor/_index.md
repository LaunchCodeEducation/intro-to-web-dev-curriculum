---
title: "1. Hello, World!"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Once you have the assignment open within visual studio code, have a look around the various files and get curious about what this code does.
Don't be afraid to look - just don't edit any of this code just yet.

After you have done some exploring, open a terminal window within your `Visual Studio Code` application. You can do this by selecting the `terminal` option near the top left of your window and clicking `new terminal`.

{{% notice blue Note "rocket" %}}
You can also open a terminal and navigate to the `assignment0` project directory location and run the following commands as well.
{{% /notice %}}

Type in the following command:

```bash
node index.js
```

You should notice that when the program runs the output is `"Hello"`. Remember, your task is to modify the output of this program so that, when run, `"Hello world!"` is printed.

Take a look at the `hello.js` file. This is the only file in your starter code that needs changing. You'll see a structure called a `function`, along with a final `module.exports` line. 

We haven't learned about either of these items yet, but we will! If you are so compelled, google these terms to get a brief introduction. If you are not compelled, you don't need to know what they do for the purposes of this class until later lessons.

{{% notice blue Tip "rocket" %}}
Set a timer for 5 mins and google search "JavaScript functions" or "JavaScript module.exports". Or look these items up directly on [W3Schools](https://www.w3schools.com/) or [MDN](https://developer.mozilla.org/en-US/). When the timer is up, write down whatever you have found interesting or most salient from your search.

Although you won't start learning about these terms in this book until later on, getting into the habit of exploring code and google searching topics helps to get you into the developer mindset.

This may not be the only place where this book leaves you with more questions than answers and getting answers from the world wide web is how every developer spends their time.
{{% /notice %}}

Back inside of `hello.js`, you should recognize a string on this line: `return "Hello!";`.

`return` is another keyword related to functions that we have not yet covered. For now, know that `return` behaves like a surrogate for `console.log()`. So anything inside of the string that follows it will be printed when your application is run.

{{% notice blue Tip "rocket" %}}
It's a good idea to take note of how this file in the starter code looks before you start editing. Changing any code other than this string may cause your program to not run properly, and therefore may not be graded correctly. Making small changes and testing them as you go makes it easier to undo changes you don't want and return to a working state.
{{% /notice %}}

With all of this in mind, modify the string on that line so that `"Hello world!"` is printed. Once you have modified the string move on to the next section!
