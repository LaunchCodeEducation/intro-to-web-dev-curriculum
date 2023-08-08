---
title: "Exercises: Chores vs. Hobbies"
date: 2023-03-31T09:42:17-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Rob Thomas 
reviewerGitHub: icre8FreeCode 
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

The following exercises walk you through the process of modifying existing
components and creating new ones.

## Starter Code

For this set of exercises, you will need a copy of the LaunchCode React
projects repository. If you haven't done so already,

1. Fork the [react-exercises-and-studios repository](https://github.com/LaunchCodeEducation/react-exercises-and-studios)
   on GitHub.
1. Clone your fork.

Navigate into the exercises now:

```console
   $ pwd
      react-projects
   $ ls
      part1 part2 part3
   $ cd part1
   $ cd exercises
```

You should be able to run  `npm start`, but the page will not look pretty. Time to fix that! 

{{% notice blue "Note" "rocket" %}}
   If the `exercises` app doesn't run at first, try running `npm install`. Once that process has completed, you should be able to run `npm start` again to get the development server going.
{{% /notice %}}

## Part 1: Modify the CSS

The `MovieList` and `ChoresList` components have been created, but so far
they appear pretty bland. Let's change that.

1. Change the movie list text by adjusting the code in
   `MovieList.module.css` to accomplish the following:

   1. The text for the heading and list items can be any color EXCEPT black.
      (HINT: Take advantage of the `movieText` class).
   1. The movie list should have heading that aligns to the *left*.
   1. The font size should be large enough to easily read.

   {{% expand "Check Your Solution" %}}

   ```css
   .movieText {
      color: purple;
      font-size: 1.3vw;
      text-align: left;
   }

   .movieHeading {
      text-align: left;
   }
   ```

   {{% /expand %}}

2. Change the chore list text by adjusting the code in
   `ChoresList.module.css` to accomplish the following:

   1. Use a different font, with a size large enough to easily read.
   1. The text color should be different from the movie list, but not black.
   1. The chores list should have an underlined heading.
   1. The chores in the list should be italicized.

### Add More Movies

The list of movies is built using an array defined in
`MovieList.js`.

3. Add two more items to the `movies` array.

   {{% expand "Check Your Solution" %}}

   ```js
   const movies = ["Pride and Prejudice", "Howl's Moving Castle", "Legally Blonde", "Star Wars"];
   ```

   {{% /expand %}}

4. Add two more `<li></li>` elements to the component
   and use JSX to reference the new movies in the array.

### Complete the `BookList` Component

5. The `BookList` component has been generated, but it is incomplete. The
   page needs more images, which also need to be smaller in size.

   1. In the `BookList` function, assign a better section heading to
      the `pageTitle` variable.
   1. The `book` variables should hold URLs for images, but only one is
      is filled in and it isn't a valid link. Update the three variables to include valid link addresses for three new book releases. To copy the URL for an image on the web, right-click
      (or control-click) on the image and select the "Copy Image Address" menu
      option.
   1. In the `return` statement for this component, use JSX in the `img`
      tags to display your chosen images and update the `alt` text to reflect what book you are linking.

      ```jsx
         <img src={book1} alt="Appropriate text for the book">
      ```

   1. Refresh the webpage to check the updated content.

   {{% expand "Check Your Solution" %}}
   
   This solution includes three books from the latest releases the week we were working on this book. Your code will have different books!

   ```jsx
   <div>
   <h3>{pageTitle}</h3>
   <img src={book1} alt="Romantic Comedy by Curtis Sittenfield" />
   <img src={book2} alt="Tress of the Emerald Sea by Brandon Sanderson" />
   <img src={book3} alt="The London Seance Society by Sarah Penner" />
   </div>
   ```

   {{% /expand %}}

Before moving on, save and commit your work.

## Part 2: Add Another Component

7. The page needs a set of links for the websites you use to keep track of or shop for your favorite hobbies.

   1. Create a new file called `HobbyLinks` for a new functional component called `HobbyLinks`.
   1. In the `HobbyLinks()` function, define the variable `hobbyLinks` and
      assign it an array that contains two or more URLs for websites that pertain to your hobbies.
   1. In the `return` statement for this component, add a set of `<a>` tags for
      the web links. Each link should be on its own line.
   1. Inside each `<a>` tag, set the `href` attribute equal to a
      placeholder for an element in the `hobbyLinks` array:

      ```jsx
         <a href = {hobbyLinks[0]}>Link text...</a>
      ```

   1. Add `<HobbyLinks />` to `App.js`. Save all of
      your changes, then refresh the page to see your new content.

   {{% expand "Check Your Solution" %}}

   ```jsx
    <div className="App">
      <MovieList />
      <ChoresList />
      <BookList />
      <HobbyLinks />
    </div>
   ```   

   {{% /expand %}}

## Part 3: Rearrange the Components

The content on the page appears quite jumbled, since we gave you no guidance on
where to put the components in `App.js`. Fortunately, templates
allow us to easily move items around the framework.

8. Rearrange the components etc. to create a specific page layout:

   1. You now have three components that could be grouped together and one that doesn't belong with the others.
      Put the odd one out at the top of the page.
   1. In `App.css`, you will find a class called `similarComponents`. Wrap the three components that go together in a `<div>` and assign it this class.

   {{% expand "Check Your Solution" %}}

   ```jsx
   <div className="App">
      <ChoresList />
      <div className="similarComponents">
        <MovieList />
        <BookList />
        <HobbyLinks />
      </div>
    </div>
   ```

   {{% /expand %}}
   
Your final page should have this format:

![Screenshot of what final page should look like](pictures/rearrange-components.png?classes=border)

### Optional Final Touches

9. To boost your practice, complete one or more of the following:

   1. Change the background of one element of a component to a decent color, image or pattern.
   1. Add a border around one or more of the components on the page.

## Sanity Check

The `react-exercises-and-studios` repository contains two branches:

1. A `main` branch with all the starter code for lessons 1, 2, and 3.
1. A `solutions` branch with completed code.

If you get stuck on a particular exercise:

1. Try again.
1. Ask your TA, instructor, classmates, or Google for tips.
1. Try again.
1. Take a break and give your brain a chance to rest.
1. Try again.
1. Feel completely justified in switching to the `solutions` branch to check
   the code.

{{% notice blue "Note" "rocket" %}}

   If you jumped right to step 6, you missed out on a stellar learning
   opportunity.

{{% /notice %}}
