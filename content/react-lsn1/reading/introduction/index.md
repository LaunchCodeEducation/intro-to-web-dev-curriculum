---
title: "Introduction"
date: 2023-03-31T09:42:17-05:00
draft: false
weight: 1
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## What is a Library and Why Would We Use One?

Many programming languages, such as JavaScript, have libraries. A **library** in programming is a collection of reusable code, such as methods and classes, that developers can use to write more complex applications more efficiently. 

When it comes to web-based applications, there are two very different places code can exist: in the user's browser (front-end) and on the host's server (back-end).

For web development, consider the front end as what the user interacts with and sees, while the back end contains the logic and manipulations that the user doesn't need to worry about. Similar to how an old mechanical clock works. The front end would be the face with the 12 numbers and the two moving hands. The user only needs the clock face to determine the time. The back end for the clock would be the various cogs, wheels, and power source.

In this chapter, we will start to use React for a front-end JavaScript library. When we create a new React application, we are given some guidelines on what structures and rules to follow, but we also have lots of freedom in determining how the application will flow. 

{{% notice blue "Note" "rocket" %}}

While some developers use the terms interchangeably, **frameworks** are different from libraries. Frameworks control the flow of the application and provide structure for it. When working with frameworks, developers do not have to make any decisions related to flow and structure and are more focused on plugging in the appropriate code at the appropriate time. An example of a front-end JavaScript framework would be Angular.

{{% /notice %}}

## React

**React** is a front-end library maintained by Meta, also known as Facebook, and an open-source community of developers/JavaScript fans. While there are many front-end frameworks and libraries that will aid you in making a beautiful website, there are a few key reasons why one may choose React over the others.

1. React is flexible enough that it can be used for cross-platform work. This means that React can be used to develop applications for mobile platforms in addition to web applications.
1. Thanks to JSX, writting HTML and JavaScript for your React application is a more straight-forward process compared to working with Angular where the code is separated into multiple files.
1. React is built on **components**, which are blocks of reusable code that we as developers write. The way React uses components makes it easy for us to call our components and reuse them in the application as we need to.

These are some of the reasons why companies, such as Netflix and Instacart, choose React. Let's dive into the final reason and learn more about components in React.
