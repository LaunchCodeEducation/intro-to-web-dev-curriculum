---
title: "Exercises: Data and Variables"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman 
reviewerGitHub: gildedgardenia 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # Wed Jul 5 08:49:19 AM CDT 2023
---

Exercises appear regularly in the book. Just like the concept checks, these exercises will check your understanding of the topics in this chapter. They also provide good practice for the new skills.

We've included our solutions to some (but not all) of the exercises so that you can check your own work after you practice. As with any learning opportunity, take it seriously and give every exercise a fair shot before peeking at the solution. Our solution may not look exactly like yours, but that's ok. There's often more than one way to solve a problem with code.

You don't need to show proof of completing the exercises to pass, so do them for your own benefit. And if they're hard or you get some answers wrong on the first try, keep going! Your future self will thank you. 

Unlike the concept checks, you will need a code editor to complete the exercises. We will be using `Visual Studio Code` as our code editor.

{{% notice blue Note "rocket" %}}
Fork and Clone the following github repository to get started: [JavaScript Projects](https://github.com/LaunchCodeEducation/javascript-projects)
{{% /notice %}}

## The Data

Use the information given below about your space shuttle to complete the
exercises:

| Data                        | Value        |
|-----------------------------|--------------|
| Name of the space shuttle   | Determination|
| Shuttle Speed (mph)         | 17,500       |
| Distance to Mars (km)       | 225,000,000  |
| Distance to the Moon (km)   | 384,400      |
| Miles per kilometer         | 0.621        |

## The Exercises

### Declare and assign variables

1. Declare and assign a variable for each item in [the Data Table]({{< relref "#the-data" >}}) above.

{{% notice blue Tip "rocket" %}}
When declaring and assigning your variables, remember that you will
need to use that variable throughout the rest of the exercises. Make sure
that you are using the correct data type!
{{% /notice %}}

{{% expand "Check Your Solution!" %}}
```javascript
let shuttleName = 'Determination';
let shuttleSpeedMph = 17500;
let distanceToMarsKm = 225000000;
let distanceToMoonKm = 38400;
const milesPerKm = 0.621;
```
{{% /expand %}}

### Print out the type of each variable

1. For each variable you declared in part A, use the ``typeof`` operator to print its type to the console, one item per line.

1. Verify your code works as expected by running the program. Once you have the correct output move on to [Calculate a space mission!]({{< relref "#calculate-a-space-mission" >}})

{{% notice blue Note "rocket" %}}
In order to run your program, open a terminal and navigate to the directory containing your `data-and-variables-exercises.js` file.

The following command will run any code within the file:

```javascript
node data-and-variables-exercises.js
```
{{% /notice %}}

### Calculate a space mission!

We need to determine how many days it will take to reach Mars.

1. Create and assign a miles to Mars variable. You can get the miles to Mars by multiplying the distance to Mars in kilometers by the miles per kilometer.

   {{% expand "Check your solution" %}}

   ```javascript
   let milesToMars = kilometersToMars * milesPerKilometer;
   ```
   {{% /expand %}}

1. Next, we need a variable to hold the hours it would take to get to Mars. To get the hours, you need to divide the miles to Mars by the shuttle's speed.

   {{% expand "Check your solution" %}}

   ```javascript
   let hoursToMars = milesToMars / shuttleSpeedMph;
   ```
   {{% /expand %}}

1. Finally, declare a variable and assign it the value of days to Mars. In order to get the days it will take to reach Mars, you need to divide the hours it will take to reach Mars by 24.

   {{% expand "Check your solution" %}}

   ```javascript
   let daysToMars = hoursToMars / 24;
   ```
   {{% /expand %}}

### Print out the results of your calculations

1. Using variables from above, print to the screen a sentence that says ``"_____ will take ___ days to reach Mars."`` Fill in the blanks with 
the shuttle name and the calculated time.

1. Verify that your code works as expected by running the program. Once you have the correct output move on to [Calculate a trip to the Moon]({{< relref "#calculate-a-trip-to-the-moon" >}})
### Calculate a trip to the Moon

Repeat the calculations, but this time determine the number of days it would take to travel to the Moon and print to the screen a sentence that says ``"_____ will take ___ days to reach the Moon."``.

{{% expand "Check Your Solution" %}}
```javascript
let milesToMoon = kilometersToMoon * milesPerKilometer;
let hoursToMoon = milesToMoon / shuttleSpeedMph;
let daysToMoon = hoursToMoon / 24;
console.log(shuttleName + " will take " + daysToMoon + " days to reach the Moon.");
```
{{% /expand %}}