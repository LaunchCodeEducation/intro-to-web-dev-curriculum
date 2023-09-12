---
title: "Require Modules"
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

In order to take advantage of modules, we must *import* them with the
**require** command. You have seen this before with `readline-sync`.

```javascript
const input = require('readline-sync');

let name = input.question("What is your name?");
console.log(`Hello, ${name}`);
```

Line 1 imports the `readline-sync` module and assigns its functions to the
`input` variable.

Modules are either *single functions* or *objects that contain multiple functions*. If importing a module returns a single function, we use the variable name to call that function. If the module returns an object, we use dot notation to call the functions stored in the object. In line 3, we see an example of this. `input.question` calls the `question` function stored in the `readline-sync` module.

Later, we will see examples of importing and using single function modules.

{{% notice blue Example "rocket" %}}
Let's check the type of `input` after we import the `readline-sync` module.

```javascript
const input = require('readline-sync');

console.log(typeof input);
```

**Console Output**

```console
object
```
{{% /notice %}}

The `readline-sync` module contains several key/value pairs, each of which
matches a key (e.g. `question`) with a specific function.

## Where Do We Find Modules?

Modules come from three places:

1. A local file on your computer.
2. Node itself, known as Core modules.
3. An external registry such as NPM.

## How Does Node Know Where to Look?

The string value passed into `require` tells Node where to look for a module.

### User Created Modules

If a module is stored on your computer, the string passed into `require` must
provide a *path* and a *filename*. This path tells Node where to find the
module, and it describes how to move up and down within the folders on your
computer. Paths can be extremely detailed, but best practice recommends that
you keep local modules either in the same folder as your project or only one
level from your project. Simple paths are better!

A **relative path** starts with `./` or `../`.

1. `./` tells Node, *Search for the module in the current project folder*.
1. `../` tells Node, *Search for the module in the folder one level UP from the project*.

As an example, let's assume we have a folder structure like:

![example path structure](pictures/path-example.png?classes=border)

Following best practice gives us three scenarios for importing one file into
another:

1. **The module is in the same folder:** If we want to import `hello.js` into `index.js`, then we add `const hello = require('./hello.js');` on line 1 of `index.js`.
1. **The module is one level up:** If we want to import ``hello.js`` into ``myCoolApp.js``, then we add ``const hello = require('../hello.js');`` on line 1 of `myCoolApp.js`.
1. **The module is one level down:** If we want to import `myCoolApp.js` into `index.js`, then we add `const coolApp = require('./Projects/myCoolApp.js');` on line 1 of `index.js`. This tells Node to search for `myCoolApp.js` in the `Projects` sub-folder, which is in the same folder as `index.js`.

### Other Modules

If the filename passed to `require` does NOT start with `./` or `../`, then Node checks two resources for the module requested.

1. Node looks for a Core module with a matching name.
1. Node looks for a module installed from an external resource like NPM.

Core modules are installed in Node itself, and as such do not require a path
description. These modules are *local*, but Node knows where to find them.
Core modules take precedence over ANY other modules with the same name.

{{% notice blue Note "rocket" %}}
[W3 schools](https://www.w3schools.com/nodejs/ref_modules.asp) provides a convenient list of the Core Node modules.
{{% /notice %}}

If Node does not find the requested module after checking Core, it looks to the
[NPM registry](https://docs.npmjs.com/about-npm/), which contains hundreds
of thousands of free code packages for developers.

In the next section, we will learn more about NPM and how to use it.

## Package.json File

Node keeps track of all the modules you import into your project. This list of
modules is stored inside a `package.json` file.

For example, if we only import `readline-sync`, the file looks something
like:

```json
{
    "main": "index.js",
    "dependencies": {
        "readline-sync": "1.4.9"
    }
}
```
{{% notice blue Note "rocket" %}}
You may not have seen or noticed the `package.json` file yet, mainly because we have not mentioned it very often up to this point. We will continue to dive a bit deeper as we progress through the book.
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Assume you have the following file structure:

![file structure example](pictures/requireCC.png?classes=border)

Which statement allows you to import the `rutabaga` module into `project.js`?

1. `const rutabaga = require('/rutabaga.js');`
1. `const rutabaga = require('./rutabaga.js');`
1. `const rutabaga = require('../rutabaga.js');`
1. `const rutabaga = require('./Tubers/rutabaga.js');`
{{% /notice %}}