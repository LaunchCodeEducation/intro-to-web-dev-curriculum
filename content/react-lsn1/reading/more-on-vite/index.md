---
title: "More on Vite"
date: 2023-03-31T09:42:17-05:00
draft: false
weight: 4
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: 
reviewerGitHub:
lastEditor: John Woolbright # update any time edits are made after review
lastEditorGitHub: jwoolbright23 # update any time edits are made after review
lastMod: 10-17-2023 # UPDATE ANY TIME CHANGES ARE MADE
---

After scaffolding your `React` application with `Vite` there are a couple of things to cover in regards to the structure of the project directory and the default `Vite` config file.

## Initial Project Structure

### index.html

the `index.html` file resides within the root folder of the application. You may have worked with different tools that scaffold the `index.html` file into the `public` directory.

With `Vite`, the `index.html` is the entry point for the entire application. Lets take a look at what is inside of the `index.html` file below:

```html {linenos=true}
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vite + React</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>
```

The above code block should certainly look familiar to boilerplate html starter code. Looking specifically at line 11:

```html
<script type="module" src="/src/main.jsx"></script>
```

This line references any `JavaScript` code within your application.

### `/src` Directory

The `/src` directory has the following default structure when creating a new `React` application:

{{< mermaid >}}
  graph TD
    subgraph src
      subgraph assets
        react.svg
      end
      App.css
      App.jsx
      index.css
      main.jsx
    end
{{< /mermaid >}}

Lets discuss the files and what they are responsible for:

1. The `main.jsx` file renders the `App.jsx` component.

   {{% notice blue Note "rocket" %}}
   Often times you may notice that an application has a `main.jsx` or `index.jsx` file. These are used interchangeably. You may notice that apps you work on in upcoming sections have an `index.jsx` file instead of a `main.jsx` file.
   {{% /notice %}}

1. The `App.jsx` component is used to call your `React` components and handle your applications routing.
1. The `App.css` file is styling specifically related to the `React` application. Syling within the `App.css` file are typically used for individual components.
1. The `index.css` file is styling file that is globally related to your entire application. If there is styling that a user wants to be used globally across the entire application and all components this is where that styling would live.

## Vite Config File

When you are starting your server from the command line, `Vite` will automatically resolve the config file called `vite.config.js` within the root directory of the project. This file is included upon scaffolding a `React` project with `Vite`. The main purpose of this file is to define the or customize how you want to serve or build your application. You can define environment variables here if you have sensitive or specific information you need to provide for the application to build.

Let's take a look at the config file below:

```javascript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],
})
```

This is the default `vite.config.js` file included with every project. It is customizable should it not suit your development needs but we will cover the default configuration.

It starts by importing the `defineConfig` function from the `vite` package. The second line imports the `react` plugin to allow `React` support within your project. It then exports the default configuration object (`defineConfig`) that was imported above, with the `react` plugin that enables your `React` code to run.

{{% notice blue Note "rocket" %}}
While you begin to work more with `Vite` and `React` keep in mind that `Vite`, like [webpack](https://webpack.js.org/), [Rollup](https://rollupjs.org/) and [Parcel](https://parceljs.org/) is a build tool that ehances the fontend development experience. Ultimately, the goal of this course is to learn basic skills for using the `React` library. If you would like to delve a bit deeper in `Vite` you can find more resources here at the [Vite Homepage](https://vitejs.dev/).
{{% /notice %}}
