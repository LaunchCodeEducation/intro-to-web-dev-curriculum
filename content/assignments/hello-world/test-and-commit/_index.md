---
title: "2. Test and Commit"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

### Test Code Locally

Run the following command to test your newly updated code to see if it passes the tests:

```bash
npm test
```

Run the program again to verify that the output is `Hello world!` as expected before moving on to the next step.

```bash
node index.js
```

### Commit Your Changes

Now that your program prints `"Hello world!"`, you'll commit your code. Committing your code is part of a process called version control, which we'll get into in a later lesson. For now, open up your terminal and type in the following commands to follow along:

1. `git status`
1. `git add .`
1. `git commit -m "Hello, world!"`
1. `git push origin main`

### Check Your Solution

Once you've committed your work, head to your Github repository associated with this assignment to see that your solution passes the tests.

The easiest way to do this is to click on the `actions` tab located near the top of your repository.

If your solution passes the grading requirements, you will also see a green check mark near your latest commit.

The latest commit message on this assignment is "removed a comma from my solution". The green check to the right of the message indicates that the solution passed.

If your solution does not pass, you will see a red `x` in its place.

The latest commit, "added a comma to my solution" does not pass the grading requirements.

A red `x` can always be corrected by repeating the previous steps. These are:

1. Open the `actions` tab. Select the failed test and select the `rerun all failed jobs` option.
1. Change the string,
1. Run the program to visually ensure that `"Hello world!"` is printed,
1. Commit and push your changes.

You may make any number of commits to your solution. You won't lose points for pushing *commit and push* many times. In fact, each assignment is worth only 1 point. In most cases, you won't need to *commit and push* more than once, however. You can verify that your code runs the way we expect by running it and seeing the proper `"Hello world!"` message printed.

In some cases, you may see a yellow dot grading status instead of the green check or red `x`. This is fine and just means that GitHub is currently building your solution. It will often resolve to either a check or `x` after a few moments.

When you see a green check, your code passes and you are all finished with the assignment.

{{% notice blue Note "rocket" %}}
If your program is outputting "Hello world!", but you are still not seeing a green check mark, make sure you did not edit any file other than `hello.js`. An accidental space or extra character can cause problems with the tests. To double check that you have not done so, you can click on the 7-digit code next to the check mark or x. This will bring up which files have been changed and any changes made. If any other files other than `hello.js` were changed, make sure to undo the changes in Repl.it and commit to Github.
{{% /notice %}}
