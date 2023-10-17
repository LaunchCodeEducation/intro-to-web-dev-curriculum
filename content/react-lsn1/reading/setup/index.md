---
title: "Create a React Application"
date: 2023-03-31T09:42:17-05:00
draft: false
weight: 3
originalAuthor: Sally Steuterman # to be set by page creator
originalAuthorGitHub: gildedgardenia # to be set by page creator
reviewer: Rob Thomas
reviewerGitHub: icre8FreeCode
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

Now that we understand more about React and components, we are ready to build a React app. To make a new React application, we will be using a front-end tool called [Vite](https://vitejs.dev/). This will allow us to scaffold a new `React` project with the required dependencies and launch a local dev server.

To get started we first need to install `vite` within the project directory.

```console
npm create vite@latest
```

You will be asked to provide a name for the project. The below example uses the name `react-part-one`.

![Image of creating a new react app with vite](pictures/npm-create-vite.png?classes=border)

You will then use your arrow keys to select the `React` option.

![Image of selecting a variant after running npm create vite@latest command](pictures/select-variant.png?classes=border)

You will then need to select the `JavaScript` variant.

![Image of complete scaffolded React project using Vite](pictures/scaffolded-project-complete.png?classes=border)

Now that your project has scaffolded you can navigate into the project root directory and run the following commands:

```bash
npm install
```

```bash
npm run dev
```

This will start your local development server and you will see output similar to the below image:

![Image of running application on localhost:5173 after executing the npm run dev command](pictures/npm-run-dev.png?classes=border)

You can view some useful Shortcuts if you press `h`

![Image of Shortcuts after pressing h which is available after executing the npm run dev command](pictures/help-command.png?classes=border)

At this point you can either open a web browser and navigate to `http://localhost:5173` or press `o` if you are within the terminal window running the application.

![Image of running react application scaffolded with Vite](pictures/running-react-application.png?classes=border)

{{% notice blue Note "rocket" %}}
You do not need to press `h` in order for the shortcuts to work. Once the app is running you can press `o` to view the application within the browser (if you are currently within the terminal window running the application).
{{% /notice %}}