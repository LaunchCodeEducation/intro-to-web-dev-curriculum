---
title: "Create a React Application"
date: 2023-03-31T09:42:17-05:00
draft: false
weight: 3
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Now that we understand more about React and components, we are ready to build a React app. To make a new React application, we will first install a tool called **Create React App**. Create React App was developed by Meta to allow developers to easily spin up React apps.

To get started we need to first install Create React App with `npm`.

```console
   npm i create-react-app
```

Now we are ready to create a new application!

```console 
   npx create-react-app new-app
```

Check that your application was properly created by navigating inside the new directory `new-app` and running the following command.

```console 
   npm start
```

Your application will be up and running! Check out the code that comes with your application by either waiting for React to open a new tab in your browser or by opening a new tab and navigating to `http://localhost:3000`. 

As you begin to edit the application, React will detect the changes you have made and automatically reload the page. To stop the local development server, type the shortcut *control+C*. To get the server going again so you can see your changes, run `npm start` again. 

## The Initial App

Open up your new React application in Visual Studio Code. In the file tree, locate these two directories: `public` and `src`. The first, `public`, holds the page template, `index.html`, and the second, `src`, is home to JavaScript and CSS files, such as `App.js` and `App.css`. When creating new files, your new files need to either go in `public` or `src` to ensure that those files are part of the build.

For this class, we will be only be editing and creating files in `src`. The `public` directory is only intended for HTML templates. In the `src` directory, you will find `index.js` and `index.css`. These files are instrumental in ensuring the project builds properly. Open up `App.js` and make note of what is already in there, including the `App` component. This is where we will begin to edit the application.
