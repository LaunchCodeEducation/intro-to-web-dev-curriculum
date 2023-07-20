# Exercises: Terminal {#terminal-exercises}

1.  If you haven\'t done so already, set up your command line
    environment with instructions from the
    `terminal-setupinstructions`{.interpreted-text role="ref"} appendix.

2.  Using your terminal, navigate to your Home directory using `cd ~`.

3.  Use `ls` to view the contents of your Home directory.

    `Check your solution <terminal-exercise-solutions3>`{.interpreted-text
    role="ref"}

4.  Use `cd` to move into your Desktop directory. For most, the command
    to do this is `cd Desktop/` since the Desktop is most often a child
    of the Home directory.

5.  In the terminal, use `mkdir` to create a folder on the Desktop
    called \'my_first_directory\'. Look on your Desktop. Do you see it?

    `Check your solution <terminal-exercise-solutions5>`{.interpreted-text
    role="ref"}

6.  Use `cd my_first_directory/` to move inside that directory.

7.  `pwd` to check your location.

    `Check your solution <terminal-exercise-solutions7>`{.interpreted-text
    role="ref"}

8.  There, make a file called \'my_first_file.txt\' with
    `touch my_first_file.txt`.

9.  Open the file and write yourself a message!

10. Back in the terminal, list the contents of your current directory
    from the terminal with `ls`.

11. Make a copy of your \'my_first_file.txt\' from it\'s current spot to
    directly on the Desktop with
    `cp my_first_file.txt ../my_first_copy.txt`.

    `Check your solution <terminal-exercise-solutions11>`{.interpreted-text
    role="ref"}

12. Move back out to your Desktop directory from the terminal with
    `cd ..`.

13. Use `ls` in the terminal to verify your \'my_first_copy.txt\' on
    your Desktop. Open it up. Is it the same as your first file?

    `Check your solution <terminal-exercise-solutions13>`{.interpreted-text
    role="ref"}

14. Move your copied file into your \'my_first_directory\' with
    `mv my_first_copy.txt my_first_directory/`.

15. Use `ls` to see that the copied file is no longer on your Desktop.

    `Check your solution <terminal-exercise-solutions15>`{.interpreted-text
    role="ref"}

16. Type `cd my_first_directory/`, followed by `ls` to confirm that your
    copy has been moved into \'my_first_directory\'.

17. `cd ..` to get back out to your Desktop.

    `Check your solution <terminal-exercise-solutions17>`{.interpreted-text
    role="ref"}

18. Type `rm -r my_first_directory/` and do a visual check, as well as
    `ls` on your terminal, to verify that the directory has been
    removed.
