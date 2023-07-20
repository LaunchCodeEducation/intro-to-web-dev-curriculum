# Events

Recall that *events* are actions that allow users to interact with the
content on a web page. Events include clicks, key presses, typing into
an input box, hovering over images, etc.

*Handling* an event performs an action that influences the DOM.

Structural directives like `*ngFor` and `*ngIf` can be combined with
events in order to add or remove content in response to user input. The
image below shows an example of this idea.

![](./figures/event-example.gif)

When the user clicks \"More\" the hidden part of the text will be
displayed. The layout of the page responds to the user\'s actions. The
click *event* is *handled* by showing more text.

## Angular Events

In the `Event Listeners <event-listeners>`{.interpreted-text role="ref"}
section of the DOM chapter, we learned the syntax for using
`addEventListener` and choosing the event we want.

Angular uses a different approach to listen for events. The event name
is placed in parentheses `()` and added inside an HTML tag. This *binds*
the event to that element.

The more common events include:

1.  `(click)`: Waits for the user to click on the element.
2.  `(keyup)`: Waits for the user to release a key.
3.  `(keydown)`: Waits for the user to press a key.
4.  `(mouseover)`: Waits for the user to move the cursor over the
    element.

### Syntax

To bind an event to an HTML tag, the general syntax is:

    <tag (event) = "statement"></tag>

The `statement` is the action we want to take when the event occurs.
This could be a function call, a variable assignment, or just a value.

::: admonition
Examples

1.  This code waits for the user to click the \"Submit\" button and then
    calls the `addData` function:

    ``` html+ng2
    <button (click) = "addData(arguments)">Submit</button>
    ```

2.  This code waits for the user to move the mouse over the element and
    then sets the `choice` variable equal to the value of `option`:

    ``` html+ng2
    <p (mouseover) = "choice = option">{{option}}</p>
    ```

3.  This code just waits for any key to be pressed:

    ``` html+ng2
    <div (keydown) = "true">Press Any Key</div>
    ```
:::
