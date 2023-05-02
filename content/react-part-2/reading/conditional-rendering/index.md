---
title: "Conditional Rendering"
date: 2023-03-22T11:39:25-05:00
draft: false
weight: 2
originalAuthor: Courtney Frey # to be set by page creator
originalAuthorGitHub: speudusa # to be set by page creator
reviewer: Kimberly Horan # to be set by the page reviewer
reviewerGitHub: codinglikeagirl42 # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

React components may need to display different things depending upon certain conditions.  This is called **Conditional Rendering**. You can create conditional to render JSX using the same JavaScript syntax you learned earlier in the course. This allows you to change the output using logical operators, such as `if` statements, `&&` operators, and the ternary operator.



maybe an weather example?
- if rainy bring umbrella?
- if sunny bring sunglasses?
- if rainy and below 32 degrees = snow!


## `if` statements

We can use `if` statements to create conditions.  Those conditions then determine the output of our application.

In the example below, we have two functions, `Rainy` and `Sunny`.  Each one returns a simple `<h1>` message.

In the `App` function, we use an `if` statement and `props` to render which statement will appear in the browser.  The `if` block starts at line 15, and declares `isRainy` as `true`.  This will return the message from the `Rainy` function.  When `isRainy` is not `true`, it will return the ` <h1>No rain today!</h1>` message instead.

{{% notice blue "Example Setting our Conditional to True" "rocket" %}}
   ```react{linenos=table,hl_lines=[14],linenostart=1}
   function Rainy(){
      return(
         <h1>Bring your umbrella!</h1>
      );
   }

   function RainOrShine(props){
      const isRainy = props.isRainy;
      if(isRainy){
         return(
            <Rainy />
         );
      }
      return(
         <h1>No rain today!</h1>
      );
   }

   export default function App(){
      return(
         <RainOrShine 
            isRainy={true}
         />
      );
   }
   ```
{{% /notice %}}

{{% expand "Output" %}}
   ## Bring your umbrella!
{{% /expand %}}



We don't always need to include the `else` statement if there are only two conditions.  
In fact, we could even compare two different functions with a single `if` statement.

In the example below, we added a second function, `Sunny` which will run if `isRainy` is not `true`.  
When `isRainy` is `false` or not `true`, the `Sunny` function will run and you will see a different message in the browser.
 
Currently, we are hardcoding these outcomes.  In the next chapter, you will learn about making this functionality more dynamic.

{{% notice blue "Example Setting our Conditional to False" "rocket" %}}
   ```react{linenos=table,hl_lines=[14],linenostart=1}
   function Rainy(){
      return(
         <h1>Bring your umbrella!</h1>
      );
   }

   function Sunny(){
      return(
         <h1>Bring your sunglasses!</h1>
      )
   }

   function RainOrShine(props){
      const isRainy = props.isRainy;
      if(isRainy){
         return(
            <Rainy />
         );
      }
      return(
         <Sunny />
      );
   }

   export default function App(){
      return(
         <RainOrShine 
            isRainy={false}
         />
      );
   }
   ```
{{% /notice %}}

{{% expand "Output" %}}
   ## Bring your sunglasses!
{{% /expand %}}

### `if/else`

What about the `else`?  In the examples above, we are not using else.
You could add an `else` block to the `RainOrShine` function.  It would have the same behavior and same output.  

{{% notice blue "Example Adding Else Block" "rocket" %}}
   ```react{linenos=table,hl_lines=[14],linenostart=1}
   function RainOrShine(props){
      const isRainy = props.isRainy;
      if(isRainy){
         return(
            <Rainy />
         );
      }
   else { return(
         <Sunny />
      );}
   }
   ```
{{% /notice %}}

## `&&` statements

The logical `&&` operator is often used with `if` blocks.  It is often used for comparison between expressions.  It will be `true` if both expression it is comparing are true.

| A  | B  | Returns |
|:---:|:---:|:---:|
| `true`  | `true`  | `true`  |
| `true`  | `false` | `false` |
| `false` | `true`  | `false` |
| `false` | `false` | `false` |

We can pair the locigal `&&` operator with an `if` statement if we want to render an element or nothing.  

We could update our `RainOrShine` function to use the logical `&&` like this:

{{% notice blue "Example setting up for logical &&" "rocket" %}}
   ```react{linenos=table,hl_lines=[14],linenostart=1}
   function RainOrShine(props){
      const isRainy = props.isRainy;
      const testWord = props.testWord;
      if((isRainy) && (testWord === "thunder")) {
         return(
            <Rainy />
         );
      }
   }
   ```
{{% /notice %}}

We would need to add the `testWord` to the `App` function.

{{% notice blue "Example: Updating App()" "rocket" %}}
```react{linenos=table,hl_lines=[14],linenostart=1}
   export default function App(){
      return(
         <RainOrShine 
            isRainy={true}
            testWord={"thunder"}
         />
      );
   }
   ```
{{% /notice %}}

{{% expand "Output" %}}
   ## Bring your umbrella!
{{% /expand %}}


If `testWord` was not `"thunder"`, then nothing would render.

{{% notice blue "Example: Updating App()" "rocket" %}}
   ```react{linenos=table,hl_lines=[14],linenostart=1}
   export default function App(){
      return(
         <RainOrShine 
            isRainy={true}
            testWord={"kangaroo"}
         />
      );
   }
   ```
{{% /notice %}}

{{% expand "Output" %}}
   ##  
{{% /expand %}}


## Ternary Operator

The **ternary operator** is a single line expression of an `if/else` statement.  

### Syntax
{{% notice blue "Example" "rocket" %}}
   ```js{linenos=table,hl_lines=[],linenostart=1}
   condition ? ifTrueExpression : ifFalseExpression
   ```
{{% /notice %}}

This would look like the following in JavaScript:
{{% notice blue "Example" "rocket" %}}
   ```js{linenos=table,hl_lines=[],linenostart=1}
   let creature = "cat";
   let creatureSound = creature = "cat" ? "Meow!" : "Woof!";  
   console.log(creatureSound)
   ```
{{% /notice %}}

{{% expand "Output" %}}
   Meow! 
{{% /expand %}}

-- rewrite the Sunny/Rainy as a ternary



## Other applications for Conditional Rendering
- using it to set styles

add styling for sunny (orange) or rainy (blue)?


## Check Your Understanding

{{% notice green  "Question" "rocket" %}} 
- if/else
{{% /notice %}}

{{% notice green  "Question" "rocket" %}} 
- ternary
{{% /notice %}}

{{% notice green  "Question" "rocket" %}} 
- && or if
{{% /notice %}}


TODO: clean this up - holding for references
## Conditional Rendering -- keep right now for articles 
 
-- they work with conditionals in JS, so maybe approach as a refactoring thing
   --https://www.w3schools.com/react/react_conditional_rendering.asp
   -- https://www.digitalocean.com/community/tutorials/7-ways-to-implement-conditional-rendering-in-react-applications

   -- https://www.freecodecamp.org/news/react-conditional-rendering/



## Types of conditionals in react -- keep right now for articles 

-- if/else
   -- https://blog.logrocket.com/react-conditional-rendering-9-methods/
   -- https://www.freecodecamp.org/news/learn-react-conditionals/
   -- https://handsonreact.com/docs/conditional-rendering
   -- https://www.w3schools.com/react/react_conditional_rendering.asp

-- ternary op.
   -- https://dev.to/ziratsu/the-ternary-operator-with-react-3b9c