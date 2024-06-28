---
title: "Exercises: Fetch"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: # set by page reviewer
reviewerGitHub: # set by page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # Wed Jul 5 08:49:19 AM CDT 2023
---

## Fetch

To practice fetching data, create a file called `fetch_planets.html` using `touch` in your terminal.

Add this preliminary HTML to your `fetch_planets` document:

```html
<!DOCTYPE html>
<html>
   <head>
      <title>Fetch Planets</title>
      <script>
         window.addEventListener("load", function(){
            // TODO: fetch planets JSON
         });
      </script>
   </head>
   <body>
      <h1>Destination</h1>
      <div id="destination">
         <h3>Planet</h3>
      </div>
   </body>
</html>
```

1. The URL where our planet data is located is: `"https://handlers.education.launchcode.org/static/planets.json"`. Add the code to fetch this URL inside the load event listener.

   {{% expand "Check Your Solution" %}}
   ```html
   window.addEventListener("load", function() {
      fetch("https://handlers.education.launchcode.org/static/planets.json").then(function(response){
         // TODO: do something after fetching and receiving a response
      });
   });
   ```
   {{% /expand %}}

1. Peek at the `response` returned in the request by adding a print statement inside of the function.

   Copy the file path of your HTML file and paste it as the URL in your browser.
   You won't see much on the page yet. Open your developer tools and examine both the 
   *Console* tab for the response value, as well as the *Network* tab for the request status.

1. Use the `.json()` method on your response now to see more of the data in the console: What data type do you see printed? 

   {{% expand "Check Your Solution" %}}
   ```html
   fetch("https://handlers.education.launchcode.org/static/planets.json").then(function(response){
      response.json().then(function(json) {
         console.log(json);
      });
   });
   ```
   {{% /expand %}}

1. Replace your `console.log(json)` with the following to view a portion of the JSON  into the app. 

   ```javascript
   const destination = document.getElementById("destination");
   destination.innerHTML = `<h3>Planet ${json[0].name}</h3>`;
   ```

   Refresh the page to see some new data in your HTML. 
   Play around by changing the index number. Does the planet name change?
   Can you change the planet's property being printed?

1. Now, what happens if we move those last lines we added to outside and after the fetch request? 
   
   Since `json` hasn't been defined outside of the 
   `response.json()` method yet, in order to move the template literal that uses
   that `json` variable, we'll need to initiate it outside of the function 
   call. Let's also put our print statement back so we can verify that our fetch works.
   
   Refresh the page and try this. See any data? See anything of note in the console?

   {{% expand "Check Your Solution" %}}
   ```html
   window.addEventListener("load", function() {
      let json = [];
      fetch("https://handlers.education.launchcode.org/static/planets.json").then(function(response){
         response.json().then(function(json) {
            console.log(json);
         });
      });
      const destination = document.getElementById("destination");
      destination.innerHTML = `<h3>Planet ${json[0].name}</h3>`;
   });
   ```
   {{% /expand %}}

{{% notice blue Note "rocket" %}}
You should not expect a response. Take note of the error that you see in the console!
{{% /notice %}}

1. Our last task left us with some knowledge about where and how we can use the  fetched data, but we don't really want to keep those changes. Instead, how  about we use an event to change the planet information we see? Let's move the DOM manipulation to inside a click handler.

   ```javascript
   fetch("https://handlers.education.launchcode.org/static/planets.json").then(function(response){
      response.json().then(function(json) {
         const destination = document.getElementById("destination");
         destination.addEventListener("click", function(){
            destination.innerHTML = `
               <div>
                  <h3>Planet ${json[0].name}</h3>
                  <img src=${json[0].image} height=250></img>
               </div>
            `;
         });
      });
   });
   ```

   Now, after refreshing the page, you can click on the `Planet` header to make the name and image appear.  Take note, we're still fetching on load, just not displaying the data until the header is clicked.

1. For fun and good measure, let's dynamically change which planet's info we're displaying each time the header is clicked. To do this, 
   - Declare a counter variable, `index` that changes each time a  `click` event takes place.
   - Use the value of `index` as the position in the planets array to use in the template literal. 
   - Finally, since we want to cap the value of `index` so that it does not exceed the length of the planets array, use a modulo to control how  large `index` can get.

   Et voila! Our destination changes on each click!

   {{% expand "Check Your Solution" %}}
   ```html
   fetch("https://handlers.education.launchcode.org/static/planets.json").then(function(response) {
      response.json().then(function(json) {
         const destination = document.getElementById("destination");
         let index = 0;
         destination.addEventListener("click", function(){
            destination.innerHTML = `
               <div>
                  <h3>Planet ${json[index].name}</h3>
                  <img src=${json[index].image} height=250></img>
               </div>
            `;
            index = (index + 1) % json.length;
         });
      });
   });
   ```
   {{% /expand %}}

![Clicking through destinations](pictures/planet-destinations.gif?classes=border)

Put on your planetary shoes. We are moving through planets!

