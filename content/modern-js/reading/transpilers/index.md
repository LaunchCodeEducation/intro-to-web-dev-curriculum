---
title: "Transpilation"
date: 2023-03-22T11:39:25-05:00
draft: false
weight: 4
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

With all the different versions of JavaScript hanging around, you might wonder how we keep it all straight. Better yet, since so many web applications run on JavaScript, how do those developers ensure that their applications still work.

Developers use **transpilers** to make their systems work. A transpiler, also called **source-to-source compiler**, takes code written in one language and compiles it into a different language. For example, a transpiler would be used to compile TypeScript into JavaScript or ES6 syntax into an older version of ECMAScript. This ensures that applications are operable on different browsers and different versions of browsers.

Compilers are also complex systems so using a transpiler can help language developers by not having them write a whole new compiler.

## Babel

**Babel** is a JavaScript transpiler. It can turn newer versions of ECMAScript code into older versions to ensure compatability with the user's environment. This helps developers immensely as they can start using the latest version without having to wait for browser support to catch up. 

Babel can also process our JSX code and help pages render properly when written in JSX. The other nice thing about Babel is that we can customize our configuration and add plugins to ensure that our TypeScript code is processed as well.