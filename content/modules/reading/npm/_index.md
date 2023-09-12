---
title: "NPM"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

**NPM**, Node Package Manager, is a tool for finding and installing Node modules. NPM has two major parts:

1. A registry of modules.
1. Command line tools to install modules.

## NPM Registry

The NPM registry is a listing of thousands of modules that are stored on a
remote server. These can be `required` and downloaded to your project. The
modules have been contributed by other developers just like you.

There is an [online version of the registry](https://www.npmjs.com/) where you can search for a module by name or desired functionality.

{{% notice blue Example "rocket" %}}
Go to [online NPM registry](https://www.npmjs.com/) and enter "readline-sync" into the search packages input box.

![Results for searching readline-sync within the NPM registry](pictures/readline-sync-npm-results.png?classes=border)

An exact match appears as the first result. That is the `readline-sync`
module we required. Clicking on the first result leads to the NPM page
that describes the `readline-sync` module.

On the details page you will see:

1. Usage statistics (how often the module is used)
1. Instructions on how to use the module (example code)
1. Version information
1. The author(s)
1. Sourcecode repository

![readline-sync npm registry homepage](pictures/readline-sync-npm-page.png?classes=border)
{{% /notice %}}

## NPM Command Line Interface (CLI)

The NPM command line tool, **CLI**, is installed with Node. The NPM CLI is used
in a computer's *terminal* to install modules into a Node project.

For now, recall that we coded many Node projects inside of Visual Studio Code.

Even though we added `readline-sync` to existing `package.json` files, our code still
required additional configuration because `input` is not defined automatically. The final step of requiring
`readline-sync` is to assign it to a variable. You may have noticed the following line or something very similar in previous chapters within your starter code for exercises, studios, or assignments.

```javascript
const input = require("readline-sync");
```

### Example Use Case

```javascript
const input = require("readline-sync");

const name = input.question("What is your name?");
console.log(`hello ${name}`);
```