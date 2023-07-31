---
title: "Task 3: Fetching Planetary Data"
date: 2023-07-07T12:55:09-05:00
draft: false
weight: 6
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer:  # to be set by the page reviewer
reviewerGitHub:  # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Finally, we need some JSON to fill in the crew on the mission destination.
Our planetary data can be found in [JSON format](https://handlers.education.launchcode.org/static/planets.json).
Review the list and decide which planet you want to send our intrepid crew to and make note of the index number.

{{% notice blue "Note" "rocket" %}} 

   When fetching more than one JSON object, we get an array of all of the JSON objects.
   In this case, that means an array of our possible mission destinations.
   When picking the mission destination, just pick the item in the array you want and start counting at 0.

{{% /notice %}}

In `scriptHelper.js`, you have three functions for this task: `myFetch()`, `pickPlanet()`, and `addDestinationInfo()`.
First, review the comments in `addDestinationInfo()`.
This is the format of the `innerHTML` for the `missionTarget` div, which you can locate using the `document` parameter of `addDestinationInfo()`.
`addDestinationInfo()` does not need to return anything.
`pickPlanet()` takes in one argument: a list of planets. Using `Math.random()`, return one planet from the list with a randomly-selected index.
`myFetch()` has some of the code necessary for fetching planetary JSON, however, it is not complete. You need to add the URL and return `response.json()`.

Now it is time to make use of these helper functions in `script.js`.  We provided some of the code necessary:

```js

   let listedPlanets;
   // Set listedPlanetsResponse equal to the value returned by calling myFetch()
   let listedPlanetsResponse;
   listedPlanetsResponse.then(function (result) {
       listedPlanets = result;
       // console.log(listedPlanets);
   }).then(function () {
       // console.log(listedPlanets);
       // Below this comment call the appropriate helper functions to pick a planet fom the list of planets and add that information to your destination.
   })
```

First, do as the comments in the code tell you and set `listedPlanetsResponse` equal to the value returned when calling `myFetch()`. This value is going to be a promise. 
If we head to our browser and open up our developer tools, we can now see a list of the planets.
Then using `pickPlanet()` and `addDestinationInfo()`, select a planet at random from `listedPlanets` and pass that information to `addDestinationInfo()`.
Reload your page and check out your site to see the mission target information.  