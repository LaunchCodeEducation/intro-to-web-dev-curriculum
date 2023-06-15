---
title: "Assignment #0 Hello, World!"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 1
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Your first assignment is mostly an exercise in following instructions. We'll ask you to modify an existing program so that, when run, the program prints "Hello world!".

Programming jobs often require you to get familiar with, or at least make use of, additional technologies. Here, you'll be using a few web applications, like GitHub and Repl.it, to write your code, run it, save it, and submit your assignment.

So while the coding task may appear straightforward, you'll be introduced to a set of instructions, or **workflow**, that is important for the rest of your success in this class.

{{% notice blue Tip "rocket" %}}
Read this whole page before you start taking any action.
{{% /notice %}}

## Requirements

1. Sign up for a GitHub account.
1. Sign up for a Repl.it account.
1. Open and accept the GitHub classroom assignment invitation.
1. Change the code in Repl.it.
1. Commit the code in Repl.it.
1. Make sure your assignment passes the test.

### GitHub

If you haven't done so already, create a [GitHub account](https://github.com/join?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home).

### Assignment Invitation

{{% notice blue Tip "rocket" %}}
Before starting on any assignment, make sure you are signed into your GitHub account!
{{% /notice %}}

First, find Assignment #0 in Canvas and click on the starter code repo link. Fork the repository to your personal profile, copy the repo’s URL for cloning, and open up Visual Studio Code.

## Hello world!

Once you have the assignment open within visual studio code, have a look around the various files and get curious about what this code does.
Don't be afraid to look - just don't edit any of this code just yet.

After you have done some exploring, use the Repl.it *Run* button to run the program. To begin with, the program prints just `"Hello"`. Remember, your task is to modify the output of this program so that, when run, `"Hello world!"` is printed.

Take a look at the `hello.js` file. This is the only file in your starter code that needs changing.
You'll see a structure called a `function`, along with a final `module.exports` line. We haven't learned about either of these items yet - but we will! If you are so compelled, google these terms to get a brief introduction.
If you are not compelled, you don't need to know what they do for the purposes of this class until later lessons.

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

With all of this in mind, modify the string on that line so that `"Hello world!"` is printed.

### Commit Your Changes

Now that your program prints `"Hello world!"`, you'll commit your code. Committing your code is part of a process called version control, which we'll get into in a later lesson. For now, go to the sidebar in your Repl.it window and click on the version control icon.

Here, the user selects the version control icon.

When you have opened the version control tab, write a commit message in the text field that prompts "What did you change?". A **commit message** is a note about what you have changed in your code.

Click on the text box and write a message that conveys what you have changed in the code.

A good commit message in this case would be something like: "Added my personal solution", or "Updated hello.js to print 'hello world!'".

Hit the *commit & push* button. Voila - your solution is submitted (pushed) to the GitHub graders.

### Check Your Solution

Once you've committed your work, head to Github to see that your solution passes the tests.

The easiest way to do this is to click on the hyperlink at the top of the Repl.it version control tab.

The hyperlink pointed to here takes you to the GitHub location of your assignment.

If your solution passes the grading requirements, you will see a green check mark near your latest commit.

The latest commit message on this assignment is "removed a comma from my solution". The green check to the right of the message indicates that the solution passed.

If your solution does not pass, you will see a red `x` in its place.

The latest commit, "added a comma to my solution" does not pass the grading requirements.

A red `x` can always be corrected by repeating the previous steps. These are:

1. Open Repl.it (you can use the *Work in Repl.it* button from the GitHub page)
1. Change the string,
1. Run the program to visually ensure that `"Hello world!"` is printed,
1. Commit and push your changes.

You may make any number of commits to your solution. You won't lose points for pushing *commit and push* many times. In fact, each assignment is worth only 1 point. In most cases, you won't need to *commit and push* more than once, however. You can verify that your code runs we expect by running it and seeing the proper `"Hello world!"` message printed.

In some cases, you may see a yellow dot grading status instead of the green check or red `x`. This is fine and just means that GitHub is currently building your solution. It will often resolve to either a check or `x` after a few moments.

When you see a green check, your code passes and you are all finished with the assignment.

{{% notice blue Note "rocket" %}}
If your program is outputting "Hello world!", but you are still not seeing a green check mark, make sure you did not edit any file other than `hello.js`. An accidental space or extra character can cause problems with Github Classroom's grading. To double check that you have not done so, you can click on the 7-digit code next to the check mark or x. This will bring up which files have been changed and any changes made. If any other files other than `hello.js` were changed, make sure to undo the changes in Repl.it and commit to Github.
{{% /notice %}}