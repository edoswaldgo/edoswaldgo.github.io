---
title: "How to Add ConEmu to Windows Context Menu"
excerpt: "Guide on how to add a context menu entry in Windows for ConEmu. This is to mimic the handy \"Git Bash Here\" feature of Git Bash."
categories:
- software
tags:
- windows
- git
- cli
---

## Overview

My blog post last week (*click [here][superpowered-gitbash] to view*) was about integrating [Git Bash for Windows][msysgit] with [ConEmu][conemu]. I forgot to include that Git Bash can add a context menu entry in Windows' explorer named, "Git Bash Here". Basically, that context menu entry will open Git Bash given the current directory of the file explorer. This feature greatly helps users who are used to navigating via GUI.

## Problem

Provided that readers have already integrated Git Bash with ConEmu, they need to start ConEmu from a default directory and navigate to their desired working directory. How can users have the "Git Bash Here" feature, but using ConEmu?

## Solution

ConEmu supports integration with the file explorer's context menu, easily. In order to add a context menu entry to Windows' File Explorer that will directly open ConEmu, may follow the steps below.

1. Open the settings dialog of ConEmu and go to *Integration*.
2. In the "*ConEmu Here*" section, specify the desired Menu Item Name.

    ```
    Menu item: ConEmu Here (Git Bash)
    ```

3. Add the command to execute upon clicking the context menu entry.

    ```
    Command: /icon "C:\Program Files\Git\etc\git.ico" /single /cmd {Git Bash}
    ```
    **Note:** `{Git Bash}` is the name of the ConEmu task created in the previous guide. This will depend on the user's created task name.
    {: .notice}

4. Define the icon desired to use when viewing the context menu entry.

    ```
    Icon file: C:\Program Files\Git\etc\git.ico
    ```

5. Click "Register".

    ![image-center](/assets/img/blog/conemu-git-bash-contextmenu/conemu-settings.png "ConEmu Settings"){: .align-center}

## Trying It Out

For testing the feature, browse any directory and follow the steps below.

1. Right click inside the file explorer window to display the context menu.
2. Click the name of the context menu, i.e. ConEmu Here (Git Bash), entry added.

    ![image-center](/assets/img/blog/conemu-git-bash-contextmenu/conemu-contextmenu.png "ConEmu Here (Git Bash)"){: .align-center}


[conemu]: http://conemu.github.io/
[msysgit]: https://gitforwindows.org/
[superpowered-gitbash]: /software/powering-git-bash-with-conemu/
