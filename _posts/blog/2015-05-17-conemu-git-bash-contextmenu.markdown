---
layout: post
title: "Add ConEmu (Git Bash) to Windows' Context Menu"
date: 2015-05-17 16:05:00
author: Ed Oswald Go
categories:
- blog
- Tips&Tricks
- Git
- Command-Line
img: conemu-git-bash-contextmenu.png
---

###Overview
My blog post last week (*Click [here][superpowered-gitbash] to view*) was about integrating [<b>Git Bash</b> by MSysGit][msysgit] with [ConEmu][conemu]. I forgot to include that Git Bash can add a context menu entry in Windows' explorer named "Git Bash Here". Basically, that context menu entry will open Git Bash given the current directory of the file explorer. This feature greatly helps users who are used to navigating via GUI.

###Problem
Provided that readers are already using the "[Superpowered Git Bash][superpowered-gitbash]" via ConEmu, they need to start ConEmu from a default directory and navigate to their desired working directory. How can users have the "Git Bash Here" feature but using ConEmu?

###Solution
[ConEmu][conemu] supports integration with the file explorer's context menu, easily. In order to add a context menu entry to Windows' File Explorer that will directly open ConEmu, may follow the steps below.

1. Open the settings dialog of ConEmu and go to Integration.
2. In the "ConEmu Here" section, specify the desired Menu Item Name.  

    *Example: ConEmu Here (Git Bash)*

3. Add the command to execute upon clicking the context menu entry.

    *Example: /icon "C:\Program Files\Git\etc\git.ico" /single /cmd {Git Bash}* 
   
    **Note:** {Git Bash} is the name of the ConEmu task created in the previous guide. This will depend on the user's created task name.

4. Define the icon desired to use when viewing the context menu entry. 

    *Example: C:\Program Files\Git\etc\git.ico*

5. Click "Register".

![alt text](/assets/img/blog/conemu-git-bash-contextmenu/conemu-settings.png "ConEmu Settings")


For testing the feature, browse any directory and follow the steps below.

1. Right click inside the file explorer window to display the context menu.
2. Click the name of the context menu, i.e. ConEmu Here (Git Bash), entry added.

![alt text](/assets/img/blog/conemu-git-bash-contextmenu/conemu-contextmenu.png "ConEmu Here (Git Bash)")

Done.

[conemu]: http://conemu.github.io/
[msysgit]: https://msysgit.github.io/
[superpowered-gitbash]: /blog/tips&amp;tricks/git/command-line/superpowered-git-bash