---
title: "Recursion Wrap-Up"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 9
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

In order to function (ba-dum chhhh), recursion must fulfill four conditions:

1. A series of small, identical steps combine to solve a larger problem.
1. A base case must be defined.  When true, this simplest case halts the recursion.
1. A recursive function repeatedly calls itself.
1. Each time the recursive function is called, it must alter the data/variables/conditions in order to move closer to the base case.

### Benefits of Recursion:

1. Fewer lines of code required to accomplish a task,
1. Makes code cleaner and more readable.

### Drawbacks of Recursion:

1. More abstract than using loops,
1. Code is "more readable" only if the reader understands recursion.

## Recursion in a Nutshell

1. Build a single function to break a big problem into a slightly smaller version of the *exact same problem*.
1. The function repeatedly calls itself to reduce the problem into smaller and smaller pieces.
1. Eventually, the function reaches a simplest case (the *base*), which it solves.
1. Solving the base case sets up the solutions to all of the previous steps.

## Why Do I Need To Know Recursion?

If you ask veteran programmers how often they use recursion, you will get
answers ranging from "Not since I had to do it in school," to "Very regularly."
Some programmers avoid recursion like the plague, while others look forward to
using it wherever it fits.

Most of the recursion problems you encounter in your tech career can be solved
with loops instead. However, *recursion is a skill most programmers will see
and are expected to know*, even if they do not use it all the time. How deep
you need to dive depends entirely on the type of job you get, your team
members, and your personal preference.

Let's use an analogy. At some point in time, most teens must "solve a
quadratic" in school (e.g. find 'x' in x :sup:`2` + 2x - 35 = 0). Perhaps you
fondly remember doing this yourself. As kids, we were *expected* to know how to
solve a quadratic, but as adults, the need to do this varies. Some of us must
frequently find x, while others only need to solve one or two equations a year.
Still others do not see quadratics again until their own kids learn about them.

Since their future jobs might not require it, why do teens need to learn how to
solve quadratics? Because at some point in time they will have to do it again
(if only to shock their kids), and they need to be ready when that happens.

The same is true for recursion.

> **Learn it.  Love it.  Use it.**