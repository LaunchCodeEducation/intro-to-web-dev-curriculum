---
title: "Setting Up Your Coding Tools"
date: 2023-07-13T13:40:55-05:00
draft: false
weight: 4
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Before you can start coding, you need to set up your coding tools.  

Be sure to create or install all of the following listed below:

## Setting Up Visual Studio Code 

For this course, you will be working in a **integrated development environment (IDE)** called Visual Studio Code.  

This is where you will write and run your code.

We have created a Visual Studio Code [installation guide]({{< relref "../../../installations/install-visual-studio/_index.md" >}}) for you to follow.

## Setting Up Your Terminal

We will be using the terminal to keep track of our code.  You will need to make sure that your terminal is set up.  

This tool is used for giving commands to your code to run or start.  This tool is also used to help track the status of your code as you work on it.  We will learn about it more in later chapters.

We have created a Terminal [installation guide]({{< relref "../../../installations/terminal-setup/_index.md" >}}) for you to follow.

## Setting Up Node.js

Once your terminal has been installed, you will need to install `Node.js`.  This will install the NPM Command Line Interface (CLI), which will allow you to run specialized commands in your terminal.  

You will use these commands to run, build, and test your JavaScript code as you work through this course.

We have created a `Node.js` [installation guide]({{< relref "../../../installations/install-node/_index.md" >}}) for you to follow.

## Setting Up Git

In the terminal we will be using Git.  Git is used for version control.  We will explore it more later in this course.  In the next section of this chapter, you will learn the basic git commands needed to work with the codebases in this course.

The Git language is best used to help you track and manage changes in your code.  We will provide you with the basic commands you need to start coding.  You will learn more about Git in later chapters.

We have created a Git [installation guide]({{< relref "../../../installations/install-git/_index.md" >}}) for you to follow.

## Creating Your GitHub Account

GitHub is an online software development platform that can store your code and help you track changes in its development using Git.  The majority of the code you will use in this course is stored in GitHub.  As an online platform, GitHub makes it easy to share code between developers, development teams, and potential employers.

We use GitHub to hold all of the **starter code** for this course.  Starter code is usually code that is lacking functionality or a complete solution.  We often provide stater code for examples, exercises, studios, and graded assignments.  You will work on completing the code as you work through this course.  You will use GitHub a lot in this course.

You will need to sign up for a free account using your email.

{{% notice green "Tip" "rocket" %}} 
   Your GitHub account username is something that you may share with other developers.  This [article](https://happygitwithr.com/github-acct.html) can offer you some guidance with deciding on your username. 
{{% /notice %}}

## Creating Your GitHub Personal Access Token (PAT)

In order to work with the starter code for this course, you will also need to create a **Personal Access Token** in GitHub which will allow you to fork and clone course repositories using _HTTPS_.  Think of it like a password just for GitHub.  We suggest creating a _Classic PAT_ for this course.  

GitHub has more information on PAT and [Managing your personal access tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens).

To create your PAT, we suggest following their walkthrough: [Creating a personal access token (classic)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic). 

A few tips when creating your PAT:
1. Provide a note about this PAT. This will help you remember what you are using it for.
1. You can set your PAT to never expire. This is not the best practice, but you are able to do it.  We suggest using the _Custom..._ option and setting it for a year.  
1. When you are asked to _Select scopes_ the only checkbox you should need is the _repo_ box.  This is the only scope you will need for this class.
1. Scroll down to the bottom of the page and click the green box to generate your new token.
1. You will see your new token.  Be sure to save your PAT somewhere secure, like a password manager and not a word document.  You will need to enter it in your terminal in order to access course repositories.  You will use it on the next page of this book, so keep it close.

Sounds like you are ready to start coding your first program.


