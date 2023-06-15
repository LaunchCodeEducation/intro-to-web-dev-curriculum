---
title: "Installing Node"
date: 2021-10-01T09:28:27-05:00
draft: false
weight: 5
---

## Setting up Node

Installing Node on your computer also installs the NPM Command Line Interface (CLI), which allows you to run specialized commands in the [terminal](#terminal-chapter).

1. Follow this link to the [Node website](https://nodejs.org/en/download/), and examine the selection screen:

2. The *LTS* version of Node is an older, reliable build that has been tested, debugged, and runs well. The *Current* version brings in newer features, but it is still being tested. Either option works for this course, but we recommend downloading the LTS version.

3. Click on the Windows or MacOS icon to download the installer to your computer. If you have a different operating system, select its 64-bit option from the list below the icons.

4. Run the installation program and follow the on-screen instructions.
- Accept the license agreement.
- When asked for the installation location, etc., use the default options.

5. Verify that the installation was successful by opening the terminal and running the command `node -v`. The output should match the version you downloaded.

```bash
$ node -v
v##.##.#
```

5. At the time of writing this walkthrough the `LTS` version of node is `18.16.0`.

6. If it doesn't install, try adding `sudo` before `npm` and then run the command again.