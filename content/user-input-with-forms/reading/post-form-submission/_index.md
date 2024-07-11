---
title: "POST Form Submission"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman 
reviewerGitHub: gildedgardenia 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## Form Submission Using POST

Instead of using GET and query parameters to submit form data, we can use POST.
To submit a form using a POST request, set the form's `method` attribute to `"POST"`.
Form data submitted via POST will be submitted in the body of the HTTP request.
Data submitted by GET requests is less secure than POST because GET request URLs
and the query parameters are cached and logged, possibly leaking sensitive data.

{{% notice blue Example "rocket" %}}
Form with `method="POST"`

```html
<form action="" method="POST">
    <label>Username <input type="text" name="username"></label>
    <label>Team Name <input type="text" name="team"></label>
    <button>Submit</button>
</form>
```
{{% /notice %}}

## Send Form Submission to a Server

The `action` and `method` attributes allows us to choose where the form request will be
sent and what type of request will be sent. How do we configure what happens in response to
a form submission?

**Form handlers** are web server actions that receive, inspect, and process requests.
They then send a response to the client. For this unit we are going to use form handlers that have already
been created for us.

{{% notice blue Example "rocket" %}}
When submitted, this form will send a POST request to the form handler defined by the
`action` attribute.

```html
<form action="https://handlers.launchcodelearning.org/request-parrot" method="POST">
    <label>Username <input type="text" name="username"></label>
    <label>Team Name <input type="text" name="team"></label>
    <button>Submit</button>
</form>
```
{{% /notice %}}

{{% notice blue "Try It!" "rocket" %}}
1. Open the `javascript-projects/user-input-with-forms/chapter-examples/form-post.html` file in a browser.
2. Open the network tab of the developer tools

![Screen shot of firefox browser with form loaded and network tab open.](pictures/network-tab-before-submission.png?classes=border)

4. Enter data into the inputs

- Type `tracking` into Username input
- Type `Requests` into Team Name input

5. Click Submit button

![Web page showing submitted values and entries in network tab.](pictures/network-tab-after-submission.png?classes=border)

Firefox browser with request handler loaded and network tab showing requests

6. Inspect the data sent in the POST request

![POST request highlited with Params tab open showing Form data](pictures/inspecting-post-request.png?classes=border)
{{% /notice %}}
   
{{% notice orange Warning "rocket" %}}
Using POST for form submissions adds a very low level of security. Using
[HTTPS](https://en.wikipedia.org/wiki/HTTPS) instead of HTTP adds a
higher level of security. Configuring HTTPS is beyond the scope of this
class.
{{% /notice %}}

## Check Your Understanding

{{% notice green Question "rocket" %}}
What attribute on `<form>` determines if the form is submitted with GET or POST?
{{% /notice %}}

{{% notice green Question "rocket" %}}
What attribute on `<form>` determines *where* the request is sent?
{{% /notice %}}