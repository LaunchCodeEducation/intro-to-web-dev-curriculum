---
title: "The map( ) Function"
date: 2023-05-03T11:39:25-05:00
draft: false
weight: 3
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---
## Resources
1. https://react.dev/learn/rendering-lists
1. https://upmostly.com/tutorials/how-to-use-map-in-react-applications
1. https://www.simplilearn.com/tutorials/reactjs-tutorial/map-in-reactjs
1. https://bobbyhadz.com/blog/react-map-with-condition

examples: https://codesandbox.io/s/eloquent-bird-ugfd6m?file=/components/SeasonSorting.js


## `map()`
`map()` is ued for iterating through or displaying lists of similar objects of a component in React.  `map()` iterates through arrays and returns JSX.  When `map()` function is called, it renders every returned value to the DOM.  This is the most popular loop used in React.
We can use the `map()` function to create lists and to iterate through arrays.  

Let's look at an example.

{{% notice blue "Example" "rocket" %}} 
In this example, we are using an array of strings that name the days of the week.  

[Try it!](https://codesandbox.io/p/sandbox/map-function-le3cw3)

   ```react{linenos=table,hl_lines=[],linenostart=1}
   let weekDays = [
      "Monday",
      "Tuesday",
      "Wednesday",
      "Thursday",
      "Friday",
      "Saturday",
      "Sunday"
   ];

   function DaysOfTheWeek() {
      const ListOfDays = (props) => {
         return props.map((day) => <li>{day}</li>);
      };
   return <ul>{ListOfDays(weekDays)}</ul>;
   }

   export default function App() {
   return (
      <div>
         <DaysOfTheWeek />
      </div>
   );
   }
   ```
 
{{% /notice %}}

{{% expand "Output Check" %}}
  - Monday
  - Tuesday
  - Wednesday
  - Thursday
  - Friday
  - Saturday
  - Sunday
{{% /expand %}}


### Keys
The example above used a simple array that contained a collection of strings.  We can use `map()` for more complicated arrays, such as an array of objects. Like the `for` loop, you can nest the `map()` function.

<!-- //TODO: link to objects page in JS textbook will need to update when JS added to this book-->

With all of the flexibility of the `map()` function, we need to ensure the correct element is rendered. `map()` works with [key-value pairs](https://education.launchcode.org/intro-to-professional-web-dev/chapters/objects-and-math/background.html). 

The key becomes a value's unique id that React associates with its component.  This helps prevent values being mixed up between components.  This unique id is crucial if the items in your array can move, be inserted into other components, or even deleted.  

It is not advised to create keys while the application is running.  Ideally, you should include them in your data somehow. A key needs to be a string or number datatype.  If you have the opportunity to create your data, we suggest using an `id` key of sorts.  If your data does not have an `id` then use what is available.

{{% notice blue "Example" "rocket" %}} 

Let's look at some data.  

We created a `calendar.json` file to store our data in our app.

TRY IT //TODO: add link
```react{linenos=table,hl_lines=[],linenostart=1}
[{
    "month": "January",
    "season": "Winter"
  },
  {
    "month": "February",
    "season": "Winter"
  },
  {
    "month": "March",
    "season": "Spring"
  }
  //continues through December
  ]
  
```
{{% /notice %}}

We have a collection of `months` and `seasons`.  We don't have any `id` values declared at this time.  Keys need to be either a number or string.  Let's use the `month` values as our keys. 

{{% notice blue "Example without ID" "rocket" %}} 
 
```react{linenos=table,hl_lines=[],linenostart=1}
   import calendar from "../components/Calendar";

   function SeasonSorting() {
   const whichSeason = calendar.map((cal) => (
      <li key={cal.month}>
         {cal.month} is part of <b>{cal.season}</b>
      </li>
   ));
   return <ol>{whichSeason}</ol>;
   }

   export default SeasonSorting;
```

{{% /notice %}}

{{% expand "Output Check" %}}
   1. January is part of Winter
   1. February is part of Winter
   1. March is part of Spring
{{% /expand %}}




{{% notice blue "Example with ID" "rocket" %}} 

```react{linenos=table,hl_lines=[],linenostart=1}
   [
   {
      "id": 1,
      "month": "January",
      "season": "Winter"
   },
   {
      "id": 2,
      "month": "February",
      "season": "Winter"
   },
   {
      "id": 3,
      "month": "March",
      "season": "Spring"
   }
   //continues to December
   ]
```

If the data had `id` key, we could use that.  In the example below, we updated the `calendar` so that each object now contains an `id`.  The output is the same.  


```react{linenos=table,hl_lines=[],linenostart=1}
   function SeasonSorting() {
   const whichSeason = calendar.map((cal) => (
      <li key={cal.id}>
      {cal.month} is part of {cal.season}
      </li>
   ));
   return <ol>{whichSeason}</ol>;
   }

      export default function App() {
      return (
         <div>
            <SeasonSorting />
         </div>
      );
      }
```
{{% /notice %}}

{{% expand "Output Check" %}}
   1. January is part of Winter
   1. February is part of Winter
   1. March is part of Spring
{{% /expand %}}

## Mapping conditions
We can also use `map()` to render array elements based on conditions.

-- see codesandbox.io for inital example


## Check Your Understanding

{{% notice green  "Question" "rocket" %}} 
- TBD
{{% /notice %}}

{{% notice green  "Question" "rocket" %}} 
- TBD
{{% /notice %}}

{{% notice green  "Question" "rocket" %}} 
- TBD
{{% /notice %}}