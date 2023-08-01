---
title: "Strings as Collections"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 1
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Throughout the first chapters of this book we have used strings to represent words or phrases we wanted to print out. Our definition of a string was simple: a string is a sequence of characters inside quotes.

In this chapter we explore strings in much more detail. Strings come with a special group of operations that can be carried out on them, known as methods. Strings are also what is called a collection data type. Let's look at what this means.

## Collection Data Types

Data types that are comprised of smaller pieces are called **collection data types**, or simply **collection types**. Depending on what we are doing, we may want to treat a value of a collection data type as a single entity (the whole collection), or we may want to access its parts.

A **character** is a string that contains exactly one element, such as `'a'`, `"?"`, or even `" "` (a single space character).

{{% notice blue Note "rocket" %}}
Some programming languages, such as Java and C, represent characters using their own data type. For example, Java has the data type `char`. JavaScript, however, does not consider strings and characters to be different types.
{{% /notice %}}

We can think of strings as being built out of characters. In this way, strings can be broken down into smaller pieces.

![The string "JavaScript" broken down into individual letters.](pictures/strings-as-collections.png?classes=border)

Strings are made up of smaller pieces, characters. Other data types, like `number` and `boolean`, are not composed of any smaller parts.

## Ordered Collections

We defined strings as *sequential* collections of characters. This means that the individual characters that make up the string are assumed to be in a particular order from left to right. The string `"LaunchCode"` is different from the string `"CodeLaunch"`, even though they contain the exact same characters.

Collection types that allow their elements to be ordered are known as **ordered collections**, for reasons that will become clear to you very soon.