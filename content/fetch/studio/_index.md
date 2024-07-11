---
title: "Studio: Fetch & JSON"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 3
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # set by page reviewer
reviewerGitHub: # set by page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # Wed Jul 5 08:49:19 AM CDT 2023
---

Your task is to build a website that shows astronauts fetched from an API.

## Get Started

1. Take a look at the starter code for the following studio located here: `javascript-projects/fetch/studio`

## Requirements

1. Add code that runs on the `window` `load` event.
    - This is done because we can't interact with the HTML elements until the page has loaded.

2. Make a GET request using `fetch` to the astronauts API `<https://handlers.launchcodelearning.org/static/astronauts.json>`__
    - Do this part inside the `load` event handler.

3. Add each astronaut returned to the web page.
    - Use the HTML template shown below.
    - Be sure to use the exact HTML including the CSS classes. (starter code contains CSS definitions)


### Example JSON

Notice that it's an array of objects, due to the outer `[` and `]`. That means you will have to
use a loop to access each object inside the JSON array.

```javascript {linenos=true}
[
    {
        "id": 1,
        "active": false,
        "firstName": "Mae",
        "lastName": "Jemison",
        "skills": [
            "Physician", "Chemical Engineer"
        ],
        "hoursInSpace": 190,
        "picture": "mae-jemison.jpg"
    },
    {
        "id": 2,
        "active": false,
        "firstName": "Frederick",
        "lastName": "Gregory",
        "skills": [
            "Information Systems", "Shuttle Pilot", "Fighter Pilot", "Helicopter Pilot", "Colonel USAF"
        ],
        "hoursInSpace": 455,
        "picture": "frederick-gregory.jpg"
    },
    {
        "id": 3,
        "active": false,
        "firstName": "Ellen",
        "lastName": "Ochoa",
        "skills": [
            "Physics", "Electrical Engineer"
        ],
        "hoursInSpace": 979,
        "picture": "ellen-ochoa.jpg"
    },
    {
        "id": 4,
        "active": false,
        "firstName": "Guion",
        "lastName": "Bluford",
        "skills": [
            "Aerospace Engineer", "Philosophy", "Physics", "Colonel USAF",
            "Fighter Pilot"
        ],
        "hoursInSpace": 686,
        "picture": "guion-bluford.jpg"
    },
    {
        "id": 5,
        "active": false,
        "firstName": "Sally",
        "lastName": "Ride",
        "skills": [
            "Physicist", "Astrophysics"
        ],
        "hoursInSpace": 343,
        "picture": "sally-ride.jpg"
    },
    {
        "id": 6,
        "active": true,
        "firstName": "Kjell",
        "lastName": "Lindgren",
        "skills": [
            "Physician", "Surgeon", "Emergency Medicine"
        ],
        "hoursInSpace": 15,
        "picture": "kjell-lindgren.jpg"
    },
    {
        "id": 7,
        "active": true,
        "firstName": "Jeanette",
        "lastName": "Epps",
        "skills": [
            "Physicist", "Philosophy", "Aerospace Engineer"
        ],
        "hoursInSpace": 0,
        "picture": "jeanette-epps.jpg"
    }
]
```

### HTML Template

Create HTML in this exact format for each astronaut, but include data about
that specific astronaut. For example the HTML below is what should be created
for astronaut Mae Jemison. All HTML created should be added to the
`<div id="container">` tag.

Do NOT copy and paste this into your HTML file. Use this as a template to
build HTML dynamically for each astronaut returned from the API.

```html
<div class="astronaut">
    <div class="bio">
        <h3>Mae Jemison</h3>
        <ul>
        <li>Hours in space: 190</li>
        <li>Active: false</li>
        <li>Skills: Physician, Chemical Engineer</li>
        </ul>
    </div>
    <img class="avatar" src="images/mae-jemison.jpg">
</div>
```

### Expected Results

After your code loads the data and builds the HTML, the web page should look
like:

![Screen shot showing what result of studio should look like.](pictures/studio-example-page.png?classes=border)

## Bonus Missions

1. Display the astronauts sorted from most to least time in space.
1. Make the "Active: true" text green, for astronauts that are still active (active is true).
1. Add a count of astronauts to the page.