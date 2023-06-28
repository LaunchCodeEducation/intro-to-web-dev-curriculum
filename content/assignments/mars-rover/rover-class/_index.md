---
title: "4. Rover Class"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 4
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

With [the Message Class section]({{< relref "../message-class/_index.md" >}}) completed, let's turn our attention to the final class, the `Rover` class.

## `Rover`

`Rover` receives a message object, updates its properties from the message, and returns the results. Remember to use TDD by first reading the class description, writing tests, and then coding the class.

### Rover Class Description

This class builds a rover object with a few properties, and it also contains a function outside of `constructor` to handle updates to its properties.

1. `constructor(position)`
   1. `position` is a number representing the rover's position.
   1. Sets `this.position` to `position`
   1. Sets `this.mode` to `'NORMAL'`
   1. Sets the default value for `generatorWatts` to 110

1. `receiveMessage(message)`
   1. `message` is a `Message` object
   1. Returns an object containing at least two properties:
      1. `message`: the name of the original `Message` object
      1. `results`: an array of *results*. Each element in the array is an object that corresponds to one `Command` in `message.commands`.
   1. Updates certain properties of the rover object
      1. Details about how to respond to different commands are in the [Command Types table](#rover-command-types).

{{% notice blue Example "rocket" %}}
```javascript
let commands = [new Command('MODE_CHANGE', 'LOW_POWER'), new Command('STATUS_CHECK')];
let message = new Message('Test message with two commands', commands);
let rover = new Rover(98382);    // Passes 98382 as the rover's position.
let response = rover.receiveMessage(message);

console.log(response);
```

**Output**

```javascript
{
   message: 'Test message with two commands',
   results: [
      {
         completed: true
      },
      {
         completed: true, 
         roverStatus: { mode: 'LOW_POWER', generatorWatts: 110, position: 98382 }
      }
   ]
}
```
{{% /notice %}}

### Rover Tests

Create `spec/rover.spec.js` and write the following tests. Write the code to make them pass in `rover.js`. Remember to use the given phrase as the test description.

**Test 7**

"constructor sets position and default values for mode and generatorWatts". Refer to the [Rover Class description](#rover-class-description) above for these default values.

**Test 8**

"response returned by receiveMessage contains the name of the message"

**Test 9**

"response returned by receiveMessage includes two results if two commands are sent in the message"

**Test 10**

"responds correctly to the status check command"

1. For the `STATUS_CHECK` command, `receiveMessage(message).results` includes a `roverStatus` object describing the current state of the rover object — `mode`, `generatorWatts`, and `position`. The test should check each of these for accuracy.
1. See the [Rover Command Types](#rover-command-types) table for more details.

**Test 11**

"responds correctly to the mode change command"

1. The test should check the `completed` property and rover mode for accuracy.
1. The rover has two modes that can be passed as values to a mode change command: 'LOW_POWER' and 'NORMAL'.

**Test 12**

"responds with a false completed value when attempting to move in LOW_POWER mode"

1. The test should check the `completed` property for accuracy and confirm that the rover's position did not change.
1. Use the [Rover Modes](#rover-modes) table for guidance on how to handle move commands in different modes.

**Test 13**

"responds with the position for the move command"

1. A `MOVE` command will update the rover's position with the position value in the command.

### Rover Command Types

| Command | Value sent with command | Updates to `Rover` object | Result returned |
|-----|-----|-----|-----|
| MOVE | Number representing the position the rover should move to. | `position` | `{completed: true}` |
| STATUS_CHECK  | No values sent with this command. | No updates | `{completed: true, roverStatus: {mode: 'NORMAL', generatorWatts: 110, position: 87382098}}` (Values for `mode`, `generatorWatts`, `position` will depend on the current state of the rover.) |
| MODE_CHANGE | String representing rover mode (see modes) | `mode` | `{completed: true}` |

**Note:**

{{% notice blue Note "rocket" %}}
The response value for `completed` will be `false` if the command could NOT be completed.
{{% /notice %}}

### Rover Modes

| Mode | Restrictions |
|-------------|--------------|
| LOW_POWER   | Can't be moved in this state. |
| NORMAL      | None |

Once your `Rover` class is complete, make sure to [Submit Your Work]({{< relref "../submitting-your-work/_index.md" >}}).
