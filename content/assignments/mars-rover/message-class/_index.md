---
title: "Task 3: Message Class"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Rob Thomas
reviewerGitHub: icre8FreeCode
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Up to this point, you have got a copy of the starter code and taken an initial dive into how the `Command` class works. Now let's turn our focus to the `Message` class!

## `Message`

Recall, the role of a message object is to bundle commands to send to the rover.

Remember with TDD, first read through the description of the class. Then read through the given tests and think about what each test means for the desired behavior of the class. Only then should you start coding the `Message` class.

### `Message` Class Description

1. This class builds an object with two properties.
    1. `constructor(name, commands)`
        1. `name` is a string that is the name of the message.
        1. `commands` is an array of `Command` objects.

{{% notice blue Example "rocket" %}}
```javascript
let commands = [new Command('MODE_CHANGE', 'LOW_POWER'), new Command('STATUS_CHECK')];
let message = new Message('Test message with two commands', commands);
```
{{% /notice %}}

### `Message` Tests

At the same level as `command.spec.js`, look for a file called `message.spec.js` and read the unit tests for the `Message` class as described below. After reading about the tests, add the necessary code to the `Message` class.

**Test 4**

This test description is "throws error if a name is NOT passed into the constructor as the first parameter". Review the first test in `command.spec.js` for an example of how this test works.

1. Look at the code in `command.js`. Use that to help you write the `Message` class in `message.js` so that your test passes. Refer to the [Message Class description]({{< relref "#message-class-description" >}}) above for more details.

**Test 5**

The description is "constructor sets name". The test confirms that the `constructor` in the `Message` class correctly sets the `name` property in a new message object.

**Test 6**

The description reads "contains a commands array passed into the constructor as the 2nd argument". This test confirms that the `commands` property of a new message object contains the data passed in from the `Message(name, commands)` call.

{{% notice orange Warning "rocket" %}}
You are moving onto the red planet now. Be prepared for fewer instructions.
{{% /notice %}}

The final class we need to work on is `Rover`. Let's check it out in [the Rover Class section]({{< relref "../rover-class/_index.md" >}}).

