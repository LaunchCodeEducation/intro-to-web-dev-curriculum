---
title: "Installing Node"
date: 2021-10-01T09:28:27-05:00
draft: false
weight: 5
---

We will need `Node.js` to run JavaScript code in our IDE.

## Setting up Node

Installing Node on your computer also installs the NPM Command Line Interface (CLI), which allows you to run specialized commands in the [terminal]({{< relref "../../terminal/reading/how-to-do-stuff" >}}).

1. Follow this link to the [Node website](https://nodejs.org/en/download/), and examine the selection screen:

1. The *LTS* version of Node is an older, reliable build that has been tested, debugged, and runs well. The *Current* version brings in newer features, but it is still being tested. Either option works for this course, but we recommend downloading the LTS version.

1. Click on the Windows or MacOS icon to download the installer to your computer. If you have a different operating system, select its 64-bit option from the list below the icons.

1. Run the installation program and follow the on-screen instructions.
   1. Accept the license agreement.
   1. When asked for the installation location, etc., use the default options.

1. Verify that the installation was successful by opening a new terminal window and running the command `node -v`. The output should match the version you downloaded.

   ```bash
   $ node -v
   v##.##.#
   ```
   {{% notice blue "Note" "rocket" %}} 
   After installing new programs, you will need to open a new terminal window to run their commands for the first time. This includes node both `Node.js` and `Git`. If you see a '_ is not recognized as an internal or external command' error (Windows) or 'command not found' error (Mac), this might be the case.
   {{% /notice %}}

   {{% notice blue "Note" "rocket" %}} 
   At the time of this walkthrough was last updated, {{< param nodeUpdateDate >}}, the `LTS` version of node is `{{< param nodeVersion >}}`. As long as your node version is `{{< param nodeShortVersion >}}` then you should not encounter any issues within this book.
   {{% /notice %}}


1. _Troubleshooting_: If it doesn't install, try adding `sudo` before `npm` and then run the command again.