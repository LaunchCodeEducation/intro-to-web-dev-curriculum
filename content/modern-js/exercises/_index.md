---
title: "Exercises: Set Up Node"
date: 2023-03-22T11:39:25-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Installing Node on your computer also installs the NPM Command Line Interface (CLI), which allows you to run specialized commands in the terminal.

1. Follow this [link](https://nodejs.org/en/download) to the Node website, and examine the selection screen.

1. The LTS version of Node is an older, reliable build that has been tested, debugged, and runs well. The Current version brings in newer features, but it is still being tested. Either option works for this course, but we recommend downloading the LTS version.

   {{% notice blue "Note" "rocket" %}}
   As of March 2023, when this page was last updated, the LTS of Node was 18.15.0
   {{% /notice %}}

1. Click on the Windows or MacOS icon to download the installer to your computer. If you have a different operating system, select its 64-bit option from the list below the icons.

1. Run the installation program and follow the on-screen instructions.

   1. Accept the licence agreement. Hopefully, doing so does not require you to give up your first born child.

   1. When asked for the installation location, etc. use the default options.

1. Verify that the installation was successful by opening the terminal and running the command node -v. The output should match the version you downloaded.

   ```console
   $ node -v
   v##.##.#
   ```

Now you have taken a major first step in starting to work with React!