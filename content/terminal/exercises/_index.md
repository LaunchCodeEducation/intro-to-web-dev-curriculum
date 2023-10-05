---
title: "Exercises"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: to be set by page reviewer
reviewerGitHub: to be set by page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

{{% notice blue Note "rocket" %}}
The following commands might already be familiar to you. Practicing them and using the commands many times over makes them second nature. Once you are comfortable with them the speed at which you can execute them and move swiftly through your terminal for common tasks becomes an excellent tool at your disposal!
{{% /notice %}}

1. Using your terminal, navigate to your Home directory using `cd ~`.

1. Use `ls` to view the contents of your Home directory.

1. Use `cd` to move into your Desktop directory. For most, the command to do this is `cd Desktop/` since the Desktop is most often a child of the Home directory.

1. In the terminal, use `mkdir` to create a folder on the Desktop called 'my_first_directory'. Look on your Desktop. Do you see it?

   {{% expand "Check Your Solution" %}}
   ![Image of terminal after changing into the desktop directory, making a directory called my_first_directory and listing directory contents](pictures/my-first-directory.png?classes=border)
   {{% /expand %}}

1. Use `cd my_first_directory/` to move inside that directory.

1. `pwd` to check your location.

1. There, make a file called 'my_first_file.txt' with `touch my_first_file.txt`.

1. Open the file and write yourself a message!

1. Back in the terminal, list the contents of your current directory from the terminal with `ls`.

   {{% expand "Check Your Solution" %}}
   ![Image of terminal after changing into my_first_directory, printing current working directory, making a file called my_first_file.txt, editing the file with vim, and listing directory contents](pictures/my-first-file.png?classes=border)
   {{% /expand %}}

1. Make a copy of your 'my_first_file.txt' from it's current spot to directly on the Desktop with `cp my_first_file.txt ../my_first_copy.txt`.

1. Move back out to your Desktop directory from the terminal with `cd ..`.

1. Use `ls` in the terminal to verify your 'my_first_copy.txt' on your Desktop. Print the contents of the file to standard out with the `cat` command. Is it the same as your first file?

   {{% expand "Check Your Solution" %}}
   ![Image of terminal after copying a file to the Desktop directory, changing into the parent directory, listing directory contents, and concatenating the contents of the copied file](pictures/my-first-copy.png?classes=border)
   {{% /expand %}}

1. Move your copied file into your 'my_first_directory' with `mv my_first_copy.txt my_first_directory/`.

1. Use `ls` to see that the copied file is no longer on your Desktop.

1. Type `cd my_first_directory/`, followed by `ls` to confirm that your copy has been moved into 'my_first_directory'.

1. `cd ..` to get back out to your Desktop.

1. Type `rm -r my_first_directory/` and do a visual check, as well as `ls` on your terminal, to verify that the directory has been removed.

   {{% expand "Check Your Solution" %}}
   ![Image of terminal after moving my_first_copy.txt to my_first_directory, listing directory contents, changing into my_first_directory, listing contents, changing back to parent directory, removing my_first_directory recursively and listing contents to verify removal](pictures/mv-first-copy.png?classes=border)
   {{% /expand %}}