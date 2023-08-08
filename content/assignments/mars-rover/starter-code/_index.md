---
title: "Task 1: Intro and Starter Code"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 1
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Rob Thomas
reviewerGitHub: icre8FreeCode
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

This task puts your unit testing, modules making, and exception handling knowledge to use by writing tests and classes for the Mars rover named Curiosity.

{{< rawhtml >}}
   <img src="pictures/curiosity-rover-selfie.png" alt="Curiosity rover taken by the rover on Mars." width=30% />
{{< /rawhtml >}}

You will create a simulation for issuing commands to Curiosity. The idea is to create a *command* at mission control, convert that command into a *message*, send it to the *rover*, then have the rover respond to that message.

We will provide descriptions of the required features you need to implement in three separate classes:

1. **Command**: A type of object containing a `commandType` property. `commandType` is one of the given strings in the table below. Some `commandTypes` are coupled with a `value` property, but not all. Every `Command` object is a single instruction to be delivered to the rover.
2. **Message**: A `Message` object has a `name` and contains several `Command` objects. `Message` is responsible for bundling the commands from mission control and delivering them to the rover.
3. **Rover**: An object representing the mars rover. This class contains information on the rover's `position`, operating `mode`, and `generatorWatts`. It also contains a function, `receiveMessage` that handles the various types of commands it receives and updates the rover's properties.

In true TDD form, you will be asked to first write the appropriate unit tests for these features, then write the code in the given class to pass those tests.

## Sections:

1. [Starter Code]({{< relref "#submitting-your-work" >}})
1. [Command Class]({{< relref "../command-class/_index.md" >}})
1. [Message Class]({{< relref "../message-class/_index.md" >}})
1. [Rover Class]({{< relref "../rover-class/_index.md" >}})
1. [Submitting Your Work]({{< relref "../submitting-your-work/_index.md" >}})

## Get the Starter Code

Fork and Clone the following repository:[Assignment #3: Mars Rover](https://github.com/LaunchCodeEducation/Mars-Rover-starter)

## How-To TDD

Recall that in TDD, you write the test for a given behavior before you code the actual function. Feel free to review the [Test/Code cycle](test-code-cycle) while you work on this project.

1. Focus on one test at a time.
1. Write the test and *then* create the code to make it pass.
1. Only write the minimum amount of code needed to make the test pass.
1. There are some constraints on how you can implement these features. A description of each class is below.

Each numbered item describes a test. *You should use the given phrases as the test descriptions* when creating your `it` statements. You must create 13 tests for this assignment.

{{% notice red Warning "rocket" %}}
Do NOT try to write all of the tests at once. Doing so will be inefficient and will cause excessive frustration.
{{% /notice %}}

Once you are ready, move on to the next section: [Command Class]({{< relref "../command-class/_index.md" >}})
