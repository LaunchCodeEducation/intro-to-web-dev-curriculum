---
title: "Visual Studio Code Installation"
date: 2021-10-01T09:28:27-05:00
draft: false
weight: 10
---

## Setting Up Visual Studio Code

Before we start coding on our computer, we need to make sure we have the right tools! Programmers use **integrated development environments (IDE)** to write and run their code. The development environment we will be using for this class is Visual Studio Code
.
In addition to simply writing and running code, Visual Studio Code has tools that recognize errors in our code and has an integrated terminal so we can navigate through our filesystem to find the files that need our attention.

{{% notice blue Note "rocket" %}}
Visual Studio Code is very customizable. Once you have everything set up, you can take additional steps to personalize your workspace such as changing the theme.
{{% /notice %}}

Go to the Visual Studio Code [download page](https://code.visualstudio.com/download/) and download the appropriate version.

## Mac Users

Please ensure that you download the correct version depending on your chip type.  If you have an _M1_ or _M2_ you are running on _Apple Silicon_.  If you have a different chip, you are most likely running on an _Intel_ chip. If you are not sure, click on the Apple icon in the top left of your screen.  Select "About this Mac".  You should see information regarding your _Chip_.  And don't hesitate to do an internet search about your chip if you are still not sure.

Open your new copy of Visual Studio Code. To open one of your coding projects, go to _File > Open_ and select the project you want to work on.

To start working with the terminal, look for the _Terminal_ tab in the top menu.  To open at new terminal,  _Terminal > New Terminal_. The new terminal window will open on the bottom of your IDE.

## Windows Users

The terminal is in powershell, not Git Bash. To change this, open the Command Palette by going to _View > Command Palette_. Type "Select Default Profile" in the search window and select "Terminal: Select Default Profile" from the menu.
Change the default to Git Bash.

Now every time you open the terminal, it will default to bash!

{{% notice blue Note "rocket" %}}
1. If Git Bash is not an option when attempting to change the terminal profile, try downloading the [Github Pull Requests and Issues extension](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github).
1. This extension comes with terminal integration.
1. Restart Visual Studio Code and then go into the Command Palette again to change the terminal profile.
{{% /notice %}}

## More Resources
You can further explore resources within Visual Studio Code by viewing the [documentation](https://code.visualstudio.com/docs).

