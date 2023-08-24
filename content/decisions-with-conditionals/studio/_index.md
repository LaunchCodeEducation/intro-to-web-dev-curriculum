---
title: "Studio: Shuttle Launch"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # Wed Jul 5 08:49:19 AM CDT 2023
---

In this studio, you are going to write code to verify that your Space Shuttle is prepared for LiftOff! This activity will combine knowledge you have gained from this chapter and the [Data and Variables Chapter]({{< relref "../../data-and-variables/_index.md" >}})

{{% notice blue Note "rocket" %}}
The starter code for this studio can be found inside of the following repository: [javascript-projects](https://github.com/LaunchCodeEducation/javascript-projects/) within the `booleans-and-conditionals` directory.
{{% /notice %}}

This studio activity will consist of 3 parts:
1. Initializing variables with shuttle specifications.
1. Writing conditional statements to check `if` your shuttle meets specific requirements and is cleared for LiftOff.
1. Verify that all conditional statements have passed in order to launch the shuttle, otherwise aborting the launch sequence.

## Initialize Variables

Start out by creating the below variables with the given values. Remember to account for different data types.

| Variable                | Value                          |
|-------------------------|--------------------------------|
| `date`                | Monday 2019-03-18              |
| `time`                | 10:05:34 AM                    |
| `astronautCount`      | 7                              |
| `astronautStatus`     | ready                          |
| `averageAstronautMassKg` | 80.7                        |
| `crewMassKg`          | `astronautCount` * `averageAstronautMassKg` |
| `fuelMassKg`          | 760,000                        |
| `shuttleMassKg`       | 74842.31                       |
| `totalMassKg`         | `crewMassKg` + `fuelMassKg` + `shuttleMassKg` |
| `maximumMassLimit`    | 850000                         |
| `fuelTempCelsius`     | -225                           |
| `minimumFuelTemp`     | -300                           |
| `maximumFuelTemp`     | -150                           |
| `fuelLevel`           | 100%                           |
| `weatherStatus`       | clear                          |
| `preparedForLiftOff`  | true                           |

## Conditional Statements

We want to make sure that the following conditions are met in order for our shuttle to launch. Create a statement for each condition:
1. if `astronautCount` is no greater than 7
1. if `astronautStatus` is ready
1. if the `totalMassKg` is less than the `maximumMassLimit` of `85000`
1. if the `fuelTempCelsius` is no less than `-300` OR no greater than `-150`
1. if `fuelLevel` is at `100%`
1. if `weatherStatus` is `clear`

## Very Shuttle is Cleared for LiftOff

Once you have completed the above conditions, print out the following shuttle information below and wish your astronauts a safe flight! If the above conditions are not met, shut down the launch operations.
1. date
1. time
1. astronautCount
1. crewMassKg
1. fuelMassKg
1. shuttleMassKg
1. totalMasskg
1. fuelTempCelsius
1. weatherStatus
1. Wish your astronauts a safe flight!

### Example Output

![Example Output of Successful Shuttle Launch](pictures/successful-shuttle-launch.png?classes=border)