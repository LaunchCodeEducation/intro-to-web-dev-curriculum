---
title: "HTML Structure"
date: 2023-09-19T14:37:14-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Programmers should follow certain rules about how to structure an HTML file.
The rules about how to structure an HTML file and the tags used to lay out this structure are vital to the browser being able to render the page.

## Structure Rules

When it comes to laying out the overarching structure of an HTML file, a programmer should follow 5 rules:

1. Every HTML file needs a `DOCTYPE` tag, specifying the HTML version used.
   When using the current version of HTML, the `DOCTYPE` tag is simple to remember as it is: `<!DOCTYPE html>`.
   This is one of few tags that does not require a closing tag.
1. The `<html>` tag denotes the beginning and end of the HTML the programmer has written.
1. The `<head>` tag contains data about the web page.
1. The `<body>` tag contains everything that appears on the page of the document.
1. The `<title>` tag goes in the `<head>` of the document and browsers require it. It gives the title of the web page that appears in the tab.

Here is an example of the structure of an HTML page based off of these rules:

```html {linenos=table}
<!DOCTYPE html>
<html>
   <head>
      <title>My Web Page</title>
      content
   </head>
   <body>
      content
   </body>
</html>
```

## Document Head

So other than the title, what goes in the head of an HTML file?
The head includes links to other files and other data about the document.
Browsers do not display the content in the head.

{{% notice blue "Note" "rocket" %}}

   The head can also include some styling to make the page beautiful.
   How to do that is covered in the next chapter on CSS.

{{% /notice %}}

## Document Body

After the programmer has written the head of the document, it is time to move on to the body of the document.
The body of the document contains the content that appears on the web page.
Within the `body` tags, programmers add images, text, and even code samples with different HTML tags.
Content outside of the body will not appear on the page.

To make HTML more readable to other programmers, programmers write comments in HTML. When adding a comment, the programmer uses `<!--` to indicate the start and `-->` to end the comment, like so:

```html {linenos=table}
<body>
   <!-- This is an important comment -->
</body>
```

{{% notice blue "Note" "rocket" %}}

   Spacing and tabs helps many programmers read through theirs and their colleagues' code.
   Be aware that doing so in HTML can affect how the browser renders the page in rare instances.

{{% /notice %}}

## Check Your Understanding

{{% notice green "Question" "rocket" %}}

   Which HTML tag does not require a closing tag?

   1. `title`
   1. `body`
   1. `head`
   1. `DOCTYPE`

{{% /notice %}}