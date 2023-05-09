---
title: "Changes in State"
date: 2023-04-12T16:25:46-05:00
draft: false
weight: 2
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

For a quick review, state is the component's memory and when a change in state occurs, the component re-renders. Let's take a more in-depth look into how React re-renders a component. First, something must trigger the re-render. In our case, we are focusing on state changes. While we can use the `useState` hook to set up a state variable, we can use the state setter function to trigger a change in state.

{{% notice orange "Warning" "rocket" %}}

   You should use the state setter function whenever you are planning on a change in state. This method ensures that the state change is recognized and the component is re-rendered.

{{% /notice %}}

So what is happening when a component re-renders in React and why does reloading the page reset the state? The answer to these questions lie in React's **Virtual DOM**. Previously, you have learned about the DOM and how events can alter the DOM.
React comes with an abstraction of the DOM that acts as a representation of what the DOM should be composed of based on the current state of the component. This representation of the DOM is called the Virtual DOM. 

When the site is first loaded or if the user reloads the page, React builds a virtual representation of the DOM based on what the component's initial state is and then builds the actual DOM that is used for the page. Now that the Virtual DOM and the DOM are both built, the site is ready for the user. As the user interacts with a component, React rebuilds the Virtual DOM and then performs a check between the Virtual DOM and the real DOM to see if there are differences. If there is a difference after a user interacts with the component, React initiates a process called **reconciliation** where the real DOM is altered to match the virtual DOM and the component is re-rendered. 

The Virtual DOM is one of the reasons why React is so efficient. Unlike the actual DOM, React's Virtual DOM only changes 
the one aspect of the whole DOM that needs to be changed. The Virtual DOM is also not responsible for directly responding to users' actions, the real DOM is. Because updating the real DOM takes more power, only updating it when there are differences between the Virtual DOM and the real DOM saves resources. 

Knowing more about how state changes, let's explore how we can update the state of a component.