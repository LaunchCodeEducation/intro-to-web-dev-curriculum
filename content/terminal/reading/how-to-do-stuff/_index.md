---
title: "How to Do Stuff in the Terminal"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## Navigating the Terminal Window

Moving from a GUI to a CLI can be difficult when we are so used to dragging our
files from one folder to another. One of the difficulties is simply figuring
out where we are in the filesystem! Here are some key indicators that the
terminal gives us to show where we are:

```bash
LaunchCode-Super-Computer:~ lcstaffmember$
```

This line is called the **prompt**. The prompt lets us know that the terminal
is ready to accept commands. `LaunchCode-Super-Computer` is the name of the
computer. The `~` tells us we are currently in the Home directory. The Home
directory is the folder that contains everything in the computer.
`lcstaffmember` is the username of the person who has logged onto the
terminal. We will be typing all of our commands after the `$`.

As we navigate through our filesystem, the terminal will rarely output a line
to let us know that the change has occurred. We have to keep our eye out on our
prompt as we enter our commands. The name of the computer and the username will
not change, however, the space where the `~` is, will. That indicates our
current directory.

## Basic Commands

There are many commands you can use in the terminal to move through the
filesystem of your computer and projects.

| Command                 | Result                                                                                                  |
|-------------------------|---------------------------------------------------------------------------------------------------------|
| `ls`                    | Lists all files and folders in the current directory.                                                   |
| `cd <new-directory>`    | `cd` stands for *change directory*. Navigates from the current directory to `new-directory`.            |
| `pwd`                   | *Print working directory*. Prints the path of the current directory.                                      |
| `mkdir <new-folder>`    | *Make directory*. Creates `new-folder` inside the current directory.                                      |
| `touch <new-file>`      | Creates a file called `new-file` in the current directory.                                                |
| `rm <old-file>`         | *Removes* `old-file` from the current directory.                                                          |
| `man <command>`         | *Manual*. Prints to the screen the manual pages for the `command`. This includes the proper syntax and a description of how that command works. |
| `clear`                 | Empties the terminal window of previous commands and output.                                               |
| `cp <source-path> <target-path>` | *Copies* the file or directory at `source-path` and puts it in the `target-path`.                      |
| `mv <source-path> <target-path>` | *Moves* the file or directory at `source-path` from its current location to `target-path`.             |

{{% notice blue Note "rocket" %}}
1. `rm` will permanently remove items from the computer and cannot be undone.
1. Git bash does not support `man`. Instead, `<command> --help` provides a scaled down alternative.
{{% /notice %}}

Beyond these basic commands, there are some shortcuts if you don't want to type
out the full name of a directory or simply can't remember it.

| Shortcut | Where it goes                           |
|----------|----------------------------------------|
| `~`      | The Home directory                     |
| `.`      | The current directory                  |
| `..`     | The parent directory of the current directory |

<!-- TODO: Need to create the terminal commands appendices section -->
For an in-depth tutorial of how to use a CLI to move through your daily life,
refer to the [terminal commands section]().

## Check Your Understanding

{{% notice green Question "rocket" %}}
What line in a CLI indicates that the terminal is ready to accept commands?

1. prompt
1. command
1. shell
1. There isn't a line that does that.

<!-- Solution: prompt -->
{{% /notice %}}

{{% notice green Question "rocket" %}}
Which shortcut takes you to the parent directory?

1. `.`
1. `~`
1. `..`

<!-- Solution: .. -->
{{% /notice %}}