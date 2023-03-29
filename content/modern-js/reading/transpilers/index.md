---
title: "Transpilation"
date: 2023-03-22T11:39:25-05:00
draft: false
weight: 4
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

With all the extensions and supersets of JavaScript, you might be wondering how developers keep track of all the different languages and versions of JavaScript. Developers make use of a process called **transpilation**. Transpilation is where a programming language is compiled into a different programming language. For example, TypeScript code can be transpiled and the end result is the equivalent JavaScript code. Developers use **transpilers**, also called **source-to-source compiler**, to make transpilation happen. Transpilers are used to ensure that applications are operable on different browsers and different versions of browsers. ECMAScript versions are not supported at the same level so a transpiler can be used to turn ES6 into ES3 to ensure that the code works for all browsers and browser versions.

## Babel

**Babel** is a JavaScript compiler transpiler. It can turn newer versions of ECMAScript code into older versions to ensure compatability with the user's environment. This helps developers immensely as they can start using the latest version of ECMAScript without having to wait for browser support to catch up. 

Babel can also process our JSX code and help pages render properly when written in JSX. The other nice thing about Babel is that we can customize our configuration and add plugins to ensure that we can use Babel with TypeScript as well. 

To start using Babel and other JavaScript tools, we need to install Node. Let's do that now.