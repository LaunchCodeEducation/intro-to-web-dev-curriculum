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

## `map()`

`map()` is used for iterating through or displaying lists of similar objects of a component in React.
The `map` function creates a new array, which it renders to the DOM.  This allows you to manipulate data from an array without changing the original array.  It is similar to any of the loops you learned in the JavaScript portion of this book.

To use the `map` function, you chain it to the array you want to iterate over.  You will need to pass it a parameter for callback.  This callback will be returned as JSX.  
Let's look at an example.

{{% notice blue "Example" "rocket" %}} 
In this example, we are using an array of strings that name the days of the week.  

We will chain the `map` function to `props` in this example. The callback parameter is `day`.  `ListOfDays` will return `day` as a list item.  `ListOfDays` is contained within the `DaysOfTheWeek` function.  The `DaysOfTheWeek` function is returning an unordered list of `ListOfDays`.  Notice in this return statement, the array `weekDays` is the parameter.

**[Try it!](https://codesandbox.io/p/sandbox/map-function-le3cw3)**

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
         return props.map((day) => <li key={props.index}>{day}</li>);
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

**Keys and Arrays**

The example above used a simple array that contained a collection of strings. The `map()` function always uses [key-value pairs](https://education.launchcode.org/intro-to-professional-web-dev/chapters/objects-and-math/background.html).  When working with an array, the key becomes the index value of the array element.  You can set the key equal to the index like we did in line 13 of the example above.

**Keys and Objects**

We can use `map()` for more complicated arrays, such as an array of objects. Like the `for` loop, you can nest the `map()` function.

<!-- //TODO: link to objects page in JS textbook will need to update when JS added to this book-->

With all of the flexibility of the `map()` function, we need to ensure it renders the correct element. 

The key becomes a value's unique id that React associates with its component.  This helps prevent values being mixed up between components.  This unique id is crucial if the items in your array can move, be inserted into other components, or even deleted.  

It is not advised to create keys while the application is running.  You should include them in your data somehow. A key needs to be a string or number data type.  If you have the opportunity to create your data, include some sort of `id` key.  If your data does not have an `id` then use what is available.

{{% notice blue "Example" "rocket" %}} 

Let's look at some data.  

We created a `calendar.json` file to store our data in our app.

**[Try It](https://codesandbox.io/p/sandbox/map-function-le3cw3?file=%2Fsrc%2FApp.js%3A1%2C4)**
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

We have a collection of `months` and `seasons`.  We don't have any `id` values declared in the JSON file.  Keys need to be either a number or string.  Let's use the `month` values as our keys. 

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

If the data had `id`, we could use that.  In the example below, we updated the `calendar` so that each object now contains an `id`.  The output is the same.  


```react{linenos=table,hl_lines=[],linenostart=1}
   import calendar from "../components/Calendar";

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
We can also use `map()` to render array elements based on conditions.  This can be useful if you do not want every item in your list rendered.  You can use any of the conditional methods addressed above.

{{% notice blue "Example mapping Conditionally" "rocket" %}} 
Let's explore how to use map and conditionals to selectively render items to the UI.

This example uses the same JSON file as the previous example.  You can explore it more in "Try It" link below.

You can code along here: **[Try It!](https://codesandbox.io/s/conditionalmapping-yds8ue)** 


```react{linenos=table,hl_lines=[],linenostart=1}
import calendar from "../components/Calendar";

let monthChoice = "August";

function ConditionInsideMap() {
  return (
    <div>
      {calendar.map((props) => {
        return props.month === monthChoice ? (
          <h2 key={props.id}>
            {props.month} is part of the {props.season} season
          </h2>
        ) : null;
      })}
    </div>
  );
}

export default ConditionInsideMap;
```
{{% /notice %}}

{{% expand "Output Check" %}}
### August is part of the Summer season
{{% /expand %}}

In the example above, we import the `calendar` and pass it to `map()`.  The `map()` function compares the `month` string to the `monthChoice` variable.  If they are equal, then the `<h2>` message will render to the screen.  Otherwise, the screen will stay blank.  This example uses a ternary operator.

## Check Your Understanding

{{% notice green  "Question" "rocket" %}} 
When the code below runs, it produces this warning: 
```bash
Warning: Each child in a list should have a unique "key" prop.
```

```react{linenos=table,hl_lines=[],linenostart=1}
const digits = [12, 65, 72, 33, 2, 99];

function ListOfNums() {
  return digits.map((number, index) => <li>{number}</li>);
}

export default ListOfNums;
```

How best can we correct our code?

1. ```react
   export default ListofNums(key={index});
   ```

1. ```react
   digits(key={index}).map
   ```
   
1. ```react
   <li key={index}>{number}</li>);
   ```

1. This will never be resolved when working with arrays.

<!-- answer: c -->
{{% /notice %}}