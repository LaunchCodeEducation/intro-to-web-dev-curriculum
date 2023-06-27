---
title: "2. Command Class"
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

## Command Class Description

We'll follow TDD practices for the creation of `Message` and `Rover`, but for this class, `Command`, we've provided the functionality. `Command` is already written for you and you do not need to modify it to write passing tests. Open up and examine the file `command.js`.

This class builds an object with two properties: `constructor(commandType, value)`
1. `commandType` is a string that represents the type of command. We will go over the details of the types when we get to the `Rover` class and tests. At this time, note that a command type will be one of the following: `MODE_CHANGE`, `MOVE`, or `STATUS_CHECK`.
1. To peek ahead at the full functionality of these types, refer to the [Command Types Table]({{< relref "../rover-class/_index.md#rover-command-types" >}}).
1. `value` is a value related to the type of command.

{{% notice blue Example "rocket" %}}
```javascript
let modeCommand = new Command('MODE_CHANGE', 'LOW_POWER');
let moveCommand = new Command('MOVE', 12000);
```

`MODE_CHANGE` and `MOVE` are passed in as the `commandType`.

`LOW_POWER` and 12000 are passed in as the `value`. Different command types require different kinds of values. `STATUS_CHECK` takes no value.

Don't worry about the mode options for now. To peek ahead, see the [Rover Modes Table]({{< relref "../rover-class/_index.md#rover-modes" >}}).
{{% /notice %}}

Now that we've gone over the class, let's check out the tests.

### Command Tests

To begin, open and examine `spec/command.spec.js`. One test has been created for you. When a user creates a new `Command` object from the class, we want to make sure they pass a command type as the first argument.

**Test 1**

Note that the test description reads, "throws error if a command type is NOT passed into the constructor as the first parameter".
<!-- TODO: Add link below that references back to the exceptions chapter example -->
1. So far, you have used many expectations to check for equality. In the chapter on exceptions, we shared an example of how we might use an expectation to check if an exception is thrown. Refer back to that [example]() for guidance on the syntax.
1. Run the command `npm test` within your terminal to verify that the test passes. Next, comment out lines 4-6 in `command.js`. Run `npm test` again to verify that the test fails (the expected error is not thrown when the `Command` class is called).
1. Restore lines 4-6 to `throw Error("Command type required.");`.
1. Change 'Command type required.' on line 9 in `command.spec.js` to 'Oops'. Run `npm test` again to verify that the test fails (the error message did not match `"Command type required."`).
1. Restore line 9 to 'Command type required.'.

**Test 2**

Create a second `Command` test using "constructor sets command type" as the description. This test checks that the `constructor` in the `Command` class correctly sets the `commandType` property in the new object.

1. Without editing `command.js`, it contains the correct code. Run `npm test` to verify that the first and second tests both pass.
1. You do not need to use `expect().toThrow()`.
1. You may not need to know the specific types of commands to write this test.

**Test 3**

Code a third test using "constructor sets a value passed in as the 2nd argument" as the description. This test checks that the `constructor` correctly sets the `value` property in the new object. You may not need to know a proper `value` in order to write this test.

Run `npm test` to verify that all 3 command tests pass.

{{% notice blue Note "rocket" %}}
As you move through the remaining instructions, the amount of guidance will decrease. Refer to your earlier, passing tests to help you construct new tests and passing code.
{{% /notice %}}

Great job, astronaut! When you are ready to keep going, check out the [Message Class]({{< relref "../message-class/_index.md" >}})!

