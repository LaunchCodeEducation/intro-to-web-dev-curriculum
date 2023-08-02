---
title: "Special Characters"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 7
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Aside from letters, numbers, and symbols, there is another class of characters
that we will occasionally use in strings, known as **special characters**.
These characters consist of special character combinations that all begin with
a `\` (backslash). They allow us to include characters in strings that would
be difficult or impossible to include otherwise, such as Unicode characters
that are not on our keyboards, control characters, and whitespace characters.

The most commonly-used special characters are `\n` and `\t`, which are the
newline and tab characters, respectively. They work as you would expect.

{{% notice blue Example "rocket" %}}
```javascript
console.log("A message\nbroken across lines,\n\tand indented");
```
**Console Output**
```console
A message
broken across lines,
    and indented
```
{{% /notice %}}

We can also represent Unicode characters (most of which aren't on a normal keyboard) using special character combinations of the form `\uXXXX`, where the Xs are combinations referenced by the [Unicode table](https://unicode-table.com/en/). This allows us to use character sets other than the basic Latin characters that English is based on, such as Greek, Cyrillic, and Arabic, as well as a wider array of symbols.

{{% notice blue Example "rocket" %}}
```javascript
console.log("The interrobang character, \u203d, combines ? and !");
```

**Console Output**

```console
The interrobang character, ‽, combines ? and !
```
{{% /notice %}}

We can also use the backslash, `\`, to include quotes within a string. This
is known as **escaping** a character.

{{% notice blue Example "rocket" %}}
```javascript
console.log("\"The dog's favorite toy is a stuffed hedgehog,\" said Chris");
```

**Console Output**


```console
"The dog's favorite toy is a stuffed hedgehog," said Chris
```
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
Which of the options below prints `'Launch'` and `'Code'` on separate
lines?

1. `console.log('Launch\nCode');`
1. `console.log('Launch/nCode');`
1. `console.log('Launch', 'Code');`
1. `console.log('Launch\tCode');`
1. `console.log('Launch/tCode');`

<!-- Solution: Option 1 -->
{{% /notice %}}