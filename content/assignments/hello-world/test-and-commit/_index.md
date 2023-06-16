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

![Image of terminal window after running the npm test command](pictures/npm-test.png?classes=border)

If your tests fail, please revisit the previous section and double check that your hello.js file is formatted as expected. The test expects the output to be "Hello world!" precisely.

### Commit Your Changes

Now that your program prints `"Hello world!"` and the tests pass, you'll commit your code. Committing your code is part of a process called version control, which we'll get into in a later lesson. For now, open up your terminal and type in the following commands to follow along:

{{% notice blue Note "rocket" %}}
You will notice in the below commands that we are also running the `git status` command to check the current status of git after running commands. It is not required that we run a `git status` command but it does help illustrate what is happening.
{{% /notice %}}

1. `git status`

![Image of terminal window after running the git status command](pictures/git-status.png?classes=border)

1. `git add .`

![Image of terminal window after running the git add . command](pictures/git-add.png?classes=border)

1. `git commit -m "Hello world!"`

![Image of terminal window after running the git commit command with "Hello World as commit message](pictures/git-commit.png?classes=border)

1. `git push origin main`

![Image of terminal window after running the git push command](pictures/git-push.png?classes=border)

### Check Your Solution

Once you've committed your work, head to your Github repository associated with this assignment to see if your solution passes the tests.

The easiest way to do this is to click on the `actions` tab located near the top of your repository.

![Image of github options within main repository page containing the actions tab](pictures/github-menu-options.png?classes=border)

Once inside of the actions tab your view should look similar to the following:

![Image of github actions view within github repository](pictures/actions-view.png?classes=border)

{{% notice blue Note "rocket" %}}
In the above image you may notice that the circle icon next to Hello world! is yellow. Your tests may have already completed by the time you navigate to this page and the circle may appear as green if the tests passed, or red if they have failed.
{{% /notice %}}

You can click on the `Hello world!` workflow run and view the steps that the `GitHub Action` is completing and receive more details:

![View after selecting the specific Hello world! workflow run within GitHub Actions](pictures/autograding-yml-view.png?classes=border)

Click the the `build` button:

![View of the actual GitHub actions build steps](pictures/build.png?classes=border)

If your solution passes the grading requirements, you will notice a check mark next to each step within the build process. You will also notice a green check mark next to your most recent `commit id` on the main page of your repository.

If your solution does not pass, you will see a red `x` in its place.

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
