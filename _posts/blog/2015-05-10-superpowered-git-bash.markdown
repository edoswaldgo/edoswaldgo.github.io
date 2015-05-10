---
layout: post
title: "Superpowered Git Bash (MSysGit)"
date: 2015-05-10 09:20:00
author: Ed Oswald Go
categories:
- blog
- Tips&Tricks
- Git
- Command-Line
img: superpowered-git-bash.png
---

###Overview
[<b>Git Bash</b> by MSysGit][msysgit] is a terminal emulator for running Git from the command-line. It provides a Linux/Unix like environment for Windows when using the "git" command.

###Why do I use it?
Git Bash brings many great features that are very helpful to Git users. Probably, the best feature it offers is the auto completion of git commands and options when pressing the "Tab" key. This feature is very helpful for starters *like me* that are not very familiar with git.

Another great feature that it provides is the color coded output. Colors let the users classify the output easily as compared to just displaying a block of text in plain white.

![alt text](/assets/img/blog/superpowered-git-bash/git-bash-features.png "Git Bash Features")

###Why I don't want to use it?
It is difficult to copy text inside Git Bash as too many clicks are need to be done. It is a must to use "Edit -> Mark" via the context menu of Git Bash in order to highlight the text to be copied.

![alt text](/assets/img/blog/superpowered-git-bash/git-bash-mark-text.png "Git Bash Mark")

###Solution
Use [ConEmu][conemu] or a different third-party terminal program that supports running of any desired shell. ConEmu supports highlighting of text via click and drag of the mouse. Please see the steps below for integrating ConEmu and Git Bash.

After installing ConEmu, open the settings dialog and *(1)* go to Startup -> Tasks . The list of predefined tasks will be displayed. *(2)* Click the "+" button in order to add Git Bash as one of the predefined tasks. *(3)* Modify the name of the new task as desired. *(4)* Specify the command to use for starting Git Bash (*may just copy the target of Git Bash properties*). *(5)* Save the settings.

![alt text](/assets/img/blog/superpowered-git-bash/conemu-settings.png "ConEmu Settings")

Create a new console dialog by clicking the "+" icon and choose the newly added ConEmu task. This will create a new tab in the ConEmu instance used.

![alt text](/assets/img/blog/superpowered-git-bash/conemu-create-console.png "ConEmu Create Console Dialog")

Done. Git Bash is now integrated with ConEmu and may now use the features of both terminal emulators.

[conemu]: http://conemu.github.io/
[msysgit]: https://msysgit.github.io/