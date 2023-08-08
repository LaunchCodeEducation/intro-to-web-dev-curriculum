---
title: "Terminal Setup"
date: 2021-10-01T09:28:27-05:00
draft: false
weight: 15
---

## Setting Up Your Terminal

Familiarizing yourself with the terminal on your machine is vital for any programmer. Over the course of this program and your career, you will find yourself navigating to it frequently.

{{% notice blue Note "rocket" %}}
You will often find yourself coming across terms such as the **terminal** and **the command line**. 

A **terminal** is a program that runs a shell which allows the user to enter commands. 

The **command-line** is any interface that allows the user to enter text-based commands. The **terminal** is an example of a command-line interface. Many programs and software have their own command-line interface in order to interact with them. For example **git** is a version control tool that has its own command-line interface that you will be using throughout the course.
{{% /notice %}}

{{% notice blue Note "rocket" %}}
Once you have your terminal setup on your machine, make sure to pin it to the taskbar or add it to your dock!
{{% /notice %}}

## Mac Users

Good news! The Terminal application comes with every Mac.

You can access it in one of two ways:

### Through the Finder

1. Open a new Finder window and navigate to the Applications folder.
1. Inside the Applications folder, you will find a Utilities folder.
1. Open the Utilities folder, and inside is the Terminal application!

### Through LaunchPad

1. If you are a fan of the LaunchPad features on Apple computers, hit the F4 key.
1. Inside the Other or Utilities folder, you can find the Terminal.

If you are still struggling to find the Terminal application, you can do a simple search in the Finder for it!

Some terminal commands require the addition of **sudo** at the front of the command. This name gives the user *super user* rights. `sudo` is often required when installing software from the terminal.

```bash
$ sudo install mocha
Password:
```

The Terminal will ask you for your machine's password.

{{% notice blue Tip "rocket" %}}
When typing, don't be alarmed if you don't see your keystrokes while typing your password. Your machine is still receiving this information.
{{% /notice %}}

Press *enter* when you are finished. If you're attempting to run a command from the terminal and receive a permissions error, check if adding `sudo` to your command will resolve the error.

## Windows Users

1. In order to get your terminal up and running, you have to first install [Git Bash](https://git-scm.com/downloads/).

   {{% notice blue Note "rocket" %}}
   When you are doing your Git Bash setup, you only need to leave the default selected.
   {{% /notice %}}

1. Once Git Bash is installed on your machine, you can find the folder for it through the Home screen.
1. Inside the folder, simply select Git Bash to open the appropriate terminal.