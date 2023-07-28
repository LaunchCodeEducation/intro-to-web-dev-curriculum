---
title: "Project Introduction"
date: 2023-06-28T13:06:26-05:00
draft: false
weight: 1
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: John Woolbright # to be set by the page reviewer
reviewerGitHub: jwoolbright23 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

You’ve learned a bit of HTML and some CSS, but you have likely only used it in bits and pieces so far, adding or modifying content in exercises or pre-existing files. Here, you are going to take another step forward by building an entire page from scratch. You will also get some practice using Git.

There are two parts to this exercise, one focused on HTML and another focused on CSS. HTML makes up the structure and content of web pages, while CSS dictates the visual style.

Best practices dictate that content and style should be kept as separate as possible. To that end, we will build the HTML portion of our page first, and afterwards we will add a few styles with CSS. We do this to avoid using HTML tags to change the general appearance of our page. For example, what if we want all of our main headings to be red? We can either add this style one time in the CSS file, or we must include `style="color:red"` in EVERY `h1` tag. Especially for large websites, CSS provides the best place to control the overall appearance of a page.

## Getting Started

Fork and clone the [Graded Assignment #4: HTML Me Something repository](https://github.com/LaunchCodeEducation/HTML-Me-Something-Start).

As always, if you need to refer back to a guide, check out [Assignment 0]({{< relref "../../hello-world/_index.md" >}}).

## Setup the Project
Open your file tree.  You should see a `__tests__` directory and some JavaScript in addition to `index.html` and `styles.css`.

   1. You should only edit `index.html` and `styles.css`
   1. The `__tests__` directory contains the autograding tests. 
   1. The remaining files are configured for the autograder. You do not need to edit these.

Before you start your project make sure you run `npm install` to pull in the necessary packages and dependencies.

The instructions for this project will have you run the tests as the final step of this project.

## Getting to Work
It’s time to build out your page! Dive into each of the two parts below:

   - [Task 1: Creating Your Content]({{< relref "./part-1/index.md" >}})
   - [Task 2: Styling]({{< relref "./part-2/index.md" >}})
   - [Task 3: Testing and Submitting Your Project]({{< relref "./part-3/index.md" >}})
