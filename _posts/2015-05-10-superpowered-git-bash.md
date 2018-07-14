---
title: "Superpowered Git Bash (MSysGit)"
categories:
- Software Development
tags:
- Git
- Command-Line
---

### Overview
[Git Bash by MSysGit][msysgit] is a terminal emulator for running Git from the command-line. It provides a Linux/Unix like environment for Windows when using the ```git``` command.

### Why do I use it?
Git Bash brings many great features that are very helpful to Git users. Probably, the best feature it offers is the auto completion of git commands and options when pressing the "Tab" key. This feature is very helpful for starters, *like me*, that are not very familiar with git. It also displays the current active branch and the state of the Git repository which is really really helpful.

Another great feature that it provides is the color coded output. Colors let the users classify the output easily as compared to just displaying a block of text in plain white.

![image-center](/assets/img/blog/superpowered-git-bash/git-bash-features.png "Git Bash Features"){: .align-center}

### Why I don't want to use it?
It is difficult to copy text inside Git Bash as too many clicks are needed to be done. It is a must to use "Edit -> Mark" via the context menu of Git Bash in order to highlight the text to be copied.

![image-center](/assets/img/blog/superpowered-git-bash/git-bash-mark-text.png "Git Bash Mark"){: .align-center}

### Solution
Use [ConEmu][conemu] or a different third-party terminal program that supports running of any desired shell. ConEmu supports highlighting of text via click and drag of the mouse. After installing ConEmu, please see the steps below for integrating ConEmu and Git Bash.

1. Open the settings dialog of ConEmu and go to Startup -> Tasks
2. Click the "+" button in order to add Git Bash as one of the predefined tasks.
3. Modify the name of the new task as desired.
4. Specify the command to use for starting Git Bash (*may just copy the target of Git Bash properties*).
5. Save the settings.

    ![image-center](/assets/img/blog/superpowered-git-bash/conemu-settings.png "ConEmu Settings"){: .align-center}

### Trying It Out
Create a new console dialog by clicking the "+" icon and choose the newly added ConEmu task. This will create a new tab in the ConEmu instance used.

![image-center](/assets/img/blog/superpowered-git-bash/conemu-create-console.png "ConEmu Create Console Dialog"){: .align-center}

Done. Git Bash is now integrated with ConEmu and may now use the features of both terminal emulators.

[conemu]: http://conemu.github.io/
[msysgit]: https://msysgit.github.io/
