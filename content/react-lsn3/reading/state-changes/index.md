---
title: "Changes in State"
date: 2023-04-12T16:25:46-05:00
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

For a quick review, state is the component's memory and when a change in state occurs, the component re-renders. Let's take a more in-depth look into how React re-renders a component. A number of things can trigger the re-render, but right now, we are going to just focus on state changes. While we can use the `useState` hook to set up a state variable, we can use the state setter function to trigger a change in state. Since state variables are treated as read-only, we cannot simply say `stateVariable = x` to update them, we have to use a state setter function to replace the current value and trigger the change in state.

So what is happening when a component re-renders in React and why does reloading the page reset the state? The answer to these questions lie in React's **Virtual DOM**. Previously, you have learned about the DOM and how events can alter the DOM.
React comes with an abstraction of the DOM that acts as a representation of what the DOM should be composed of based on the current state of the component. This representation of the DOM is called the Virtual DOM. 

When the site is first loaded or if the user reloads the page, React builds from scratch a virtual representation of the DOM based on what the component's initial state is and then builds the actual DOM that is used for the page, which is used to display the app to the user. Now that the Virtual DOM and the DOM are both built, the site is ready for the user. As the user interacts with a component, React rebuilds the Virtual DOM and then performs a check between the Virtual DOM and the real DOM to see if there are differences. If there is a difference after a user interacts with the component, React initiates a process called **reconciliation** where the real DOM is altered to match the virtual DOM and the component is re-rendered. 

The Virtual DOM is one of the reasons why React is so efficient. Unlike the actual DOM, React's Virtual DOM only changes 
the one aspect of the DOM that needs to be changed as opposed to rebuilding the entire DOM. Because updating the real DOM takes more power, only updating it when there are differences between the Virtual DOM and the real DOM saves resources.  Also, the real DOM is responsible for directly responding to the users' actions, while the Virtual DOM is an abstract construction built by React that the user cannot interact with.
 
Knowing more about how state changes, let's explore how we can update the state of a component with code.

## Check Your Understanding

{{% notice green "Question" "rocket" %}}

True/False: The Virtual DOM is responsible for responding directly to the user.

{{% /notice %}}

<!-- False -->

{{% notice green "Question" "rocket" %}}

True/False: The process of checking the Virtual DOM against the real DOM and updating the real DOM to match is called reconciliation.

{{% /notice %}}

<!-- True -->