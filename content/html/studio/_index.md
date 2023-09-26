---
title: "Studio: Making Headlines"
date: 2023-09-19T14:37:14-05:00
draft: false
weight: 3
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## Getting Ready: Developer Tools

Firefox's developer tools contain a lot of functionality, and we will only begin to touch on it here, 
learning more of its functionality later in the unit. In this class, we'll learn about the tools available for working with HTML elements.

As you've learned, debugging is an essential part of coding. When it comes to debugging web pages, browser developer tools are indispensable.

This studio requires you to use Firefox's developer tools. In particular, you should be able to:

1. Open Firefox's dev tools
1. Inspect an HTML element
1. Modify an element's HTML
1. Explain the difference between the content displayed when using *View Source* and what you see in the *Inspector* tab

{{% notice blue "Note" "rocket" %}}

The [full documentation](https://developer.mozilla.org/en-US/docs/Tools) for Firefox's developer tools covers these items, and much more.

{{% /notice %}}

## Studio

Pick a news site ([The New York Times](https://www.nytimes.com/), for example), and use your browser's developer tools to modify one of the main articles to use a picture and text of your choosing.

Have fun with this, but be respectful of others and avoid overtly critical political or social commentary.

You might do something like this:

![A screenshot of the New York Times website, with a fake article announcing an astronaut apprenticeship program at LaunchCode.](pictures/making-headlines-screenshot.png)

### Image URLs

When linking to an image, pay attention to the protocol of both the site you are modifying and of the image you are including. The protocol will be either `http` or `https`.

If the site loads over `https` and your image uses `http` then the image may not load properly due to browser security restrictions. You should try to add `s` to the image protocol, and if that doesn't work, look for another image.

## Resources

* [Using Firefox Page Inspector](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector)
* [Firefox DevTools Documentation](https://developer.mozilla.org/en-US/docs/Tools)

## Bonus Mission

Try adding your own image! If you want to use an image of your own that is not already available via the internet, here's how:

1. Upload the photo to a [Dropbox](https://www.dropbox.com/) account. You can use Dropbox Basic for this!
1. View the photo on Dropbox and select *Share*, then *Get link*, then *Go to link*
1. You should now be viewing the image on the Dropbox site. If the URL contains `?dl=0`, remove it. Add `?raw=1` to the end of the URL in the location bar of your browser and hit *Enter*. The URL should look something like this:

   ```console
   https://www.dropbox.com/sc/qc3htnhv7fb3i2x/AAC5OzECOyBynstMDWawCZhxa?raw=1
   ```

1. Copy the URL of the loaded image. You can use this URL within any HTML.