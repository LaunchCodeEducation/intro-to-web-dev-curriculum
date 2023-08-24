---
title: "Encoding Characters"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 6
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

If you had microscope powerful enough to view the data stored on a computer's
hard drive, or in its memory, you would see lots of 0s and 1s. Each such 0 and
1 is known as a **bit**. A bit is a unit of measurement, like a meter or a
pound. Collections of computer data are measured in bits; every letter, image,
and pixel you interact with on a computer is represented by bits.

We work with more complex data when we program, including numbers and strings.
This section examines how such data is represented within a computer.

## Representing Numbers

A **byte** is a set of 8 bits. Bytes look like 00101101 or 11110011, and they
represent a **binary number**, or a base-2 number. A binary number is a number
representation that uses only 0s and 1s. The numbers that you are used to,
which are built out of the integers 0...9, are **decimal numbers**, or base-10
numbers.

Since each bit can have one of two values, each byte can have one of `8` = 256 different values.

It may not be obvious, but every decimal integer can be represented as a binary
integer, and vice versa. There are 256 different values a byte may take, each
of which can be used to represent a decimal integer, from 0 to 255.

{{% notice blue Note "rocket" %}}
We will not go into binary to decimal number conversion. If you are
interested in learning more, there are [many](https://www.binaryhexconverter.com/binary-to-decimal-converter) [tutorials](https://www.youtube.com/watch?v=wPvI19DmWQw) [online](https://www.khanacademy.org/math/algebra-home/alg-intro-to-algebra/algebra-alternate-number-bases/v/decimal-to-binary) that can show you the way.
{{% /notice %}}

In this way, the bits in a computer can be viewed as integers. If you want to
represent values greater than 255, just use more bits!

## Representing Strings

Strings are collections of characters, so if we can represent each character
as a number, then we'll have a way to go from a string to a collection of bits,
and back again.

### Character Encodings

Unlike the natural translation between binary and decimal numbers, there is no
natural translation between integers and characters. For example, you might
create a pairing of 0 to `a`, 1 to `b`, and so on. But what integer should
be paired with `$` or a tab? Since there is no natural way to translate
between characters and integers, computer scientists have had to make such
translations up. Such translations are called **character encodings**.

There are many different encodings, some of which continue to evolve as our use
of data evolves. For instance, the most recent versions of the Unicode
character encoding include emoji characters, such as 🌮.

### The ASCII Encoding

Most of the characters that you are used to using---including letters, numbers,
whitespace, punctuation, and symbols---are part of the **ASCII** (pronounced
*ask-ee*) character encoding. This standard has changed very little since the
1960s, and it is the foundation of all other commonly-used encodings.

{{% notice blue Note "rocket" %}}
ASCII stands for American Standard Code for Information Interchange, but
most programmers never remember that, so you shouldn't try to either.
{{% /notice %}}

ASCII provides a standard translation of the most commonly-used characters to
one of the integers 0...127, which means each character can be stored in a
computer using a single byte.

ASCII maps `a` to 97, `b` to 98, and so on for lowercase letters, with `z` mapping to 122. Uppercase letters map to the values 65 through 90. The other integers between 0 and 127 represent symbols, punctuation, and other assorted odd characters. This scheme is called the **ASCII table**, and rather than replicate it here, we refer you to an [excellent one online](https://www.ascii-code.com/).

In summary, strings are stored in a computer using the following process:

1. Break a string into its individual characters.
1. Use a character encoding, such as ASCII, to convert each of the characters to an integer.
1. Convert each integer to a series of bits using decimal-to-binary integer conversion.

{{% notice blue "Fun Fact" "rocket" %}}
JavaScript uses the UTF-16 encoding, which includes ASCII as a subset. We will rarely need anything outside of its ASCII subset, so we will usually talk about "ASCII codes" in JavaScript.
{{% /notice %}}

## Character Encodings in JavaScript

JavaScript provides methods to convert any character into its ASCII code and
back.

The string method `charCodeAt` takes an index and returns the ASCII code of
the character at that index.

{{% notice blue Example "rocket" %}}

```javascript
let nonprofit = "LaunchCode";

console.log(nonprofit.charCodeAt(0));
console.log(nonprofit.charCodeAt(1));
console.log(nonprofit.charCodeAt(2));
console.log(nonprofit.charCodeAt(3));
console.log(nonprofit.charCodeAt(4));
console.log(nonprofit.charCodeAt(5));
console.log(nonprofit.charCodeAt(6));
console.log(nonprofit.charCodeAt(7));
console.log(nonprofit.charCodeAt(8));
console.log(nonprofit.charCodeAt(9));
```

**Console Output**

```console
76
97
117
110
99
104
67
111
100
101
```
{{% /notice %}}

To convert an ASCII code to an actual character, use `String.fromCharCode()`.

{{% notice blue Example "rocket" %}}
```javascript
let codes = [76, 97, 117, 110, 99, 104, 67, 111, 100, 101];

let characters = String.fromCharCode(codes[0]) + String.fromCharCode(codes[1])
                + String.fromCharCode(codes[2]) + String.fromCharCode(codes[3])
                + String.fromCharCode(codes[4]) + String.fromCharCode(codes[5])
                + String.fromCharCode(codes[6]) + String.fromCharCode(codes[7])
                + String.fromCharCode(codes[8]) + String.fromCharCode(codes[9]);

console.log(characters);

```

**Console Output**

```console
LaunchCode
```
{{% /notice %}}