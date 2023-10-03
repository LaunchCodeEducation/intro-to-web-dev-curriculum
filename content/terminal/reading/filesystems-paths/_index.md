---
title: "Filesystem and Paths"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

A **filesystem** is a structure for the computer to store the files and folders
that make up the data of the operating system.

Inside a filesystem, folders are referred to as **directories**. Folders that exist inside other folders are 
called **subdirectories**. A **root directory** can refer to a few different things but essentially means the 
top-most directory of a given system. In other words, a root directory is not a sub-directory - but it will probably 
contain its own subdirectories. Inside the machine you work with, the root directory is the 
location of primary hard drive - in Windows, that's your C drive; in a Mac, the root directory is represented as `/`.
The root directory is the **parent directory** for the folders stored inside of it.

{{% notice blue Example "rocket" %}}
Most of you have a `Desktop` folder on your computer. If you happened to store your `javascript-projects` folder on your Desktop, then the parent directory of `javascript-projects` is `Desktop`.
{{% /notice %}}

A **path** for files and folders is the list of parent directories that the computer must go through to find that particular item.

Filesystems have two different types of paths: absolute and relative. The **absolute path** is the path to a file from the root directory.
The **relative path** is the path to a file from the current directory. When working with a relative path, you may find yourself wanting to go up into a parent directory to find a file in a different sub, or child, directory. In order to do so, you can use `..` in the file path to tell the computer to go up to the parent directory.

Below you will find examples for both scenarios.

## Absolute Path

{{% notice blue Example "rocket" %}}
Envision a scenario where there is a file called `homework.js` located within the `Desktop` directory.

The absolute path for `homework.js` would be `/Users/launchcode-learner/Desktop/homework.js` for Mac users.

The absolute path for `homework.js` would be `C:\windows\Desktop\homework.js` for Windows users.
{{% /notice %}}

The following screenshot was taken on a `Linux` machine where the absolute path for `homework.js` is `/home/john/Desktop/homework.js`. The user in the screenshot utilizes the `pwd` command to display the current working directory and the `ls` command to list the contents of that directory. You will learn about these commands and more in the next section.

![Example image of desktop directory on linux machine using the pwd and ls command to demonstrate the absolute path for homework.js](pictures/absolute-path.png?classes=border)

## Relative Path

{{% notice blue Example "rocket" %}}
Using the image below we will cover an example for a relative path:

![Image of a Desktop file tree that has three subdirectories.](pictures/file-tree-example.png?classes=border)

Envision that the user is located within the `java/spring-boot` directory but they needed to copy the `javascript` file from the `launchcode/curriculum` directory. The relative path for this scenario is `../../launchcode/curriculum/javascript`. 

The following command would accomplish the above task:

```bash
cp ../../launchcode/curriculum/javascript .
```
{{% /notice %}}

Remember that the **relative path** is always going to be the path to your `desired` location from your `current` location.

Many programmers use paths to navigate through the filesystem in the terminal.
We will discuss the commands to do so in the next section.