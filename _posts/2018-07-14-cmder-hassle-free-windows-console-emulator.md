---
title: "Cmder: A Hassle-free Console Emulator for Windows"
excerpt: "Cmder is built on top of the great ConEmu but packed with more features and appealing look. Head down to the article and see if Cmder can be your best console emulator for Windows."
categories:
- software
tags:
- windows
- git
- cli
---

### Overview

I spent most of my coding career using Windows but last 2016, I needed to start using [Mac OS X][osx] full-time. The transition is quite smooth but one should get use to pressing the Command Key (`⌘`) instead of Control (`Ctrl`). After I got used to it, the ergonomic experience felt more natural as less hand re-positioning is needed.

Aside from typing experience, one major thing I like with OS X is the Unix command line. The commands are quite powerful and detailed. Also, if the user has experience with Linux, he/she would not have any problem in using the command-line of OS X.

Due to some circumstance, I needed to use Windows again as my development environment. How will I transition back to Windows? Am I doomed? *\*sobs\**

### Questions

1. Should I just use the Windows Command Prompt? *Definitely \*pause\* not.*

2. How can I have access to Unix commands in Windows?

3. Should I just follow my old setup of ConEmu + Git Bash?

4. Is there a more convenient tool or setup especially for software developers using Windows?

5. How about the pleasing user interface from OS X?

### Discovery

Upon setting up my development environment for Windows, luckily, I found the [Cmder][cmder] tool!

{% include figure image_path="http://cmder.net/img/main.png" alt="Cmder" caption="Reference Image from http://cmder.net/" %}

The tool answered all the concerns I mentioned on the previous section. Below are some of its features that I super duper love.

1. Built on top [ConEmu][conemu]

    * Accessible ConEmu goodies i.e. tabs, tabs, tabs, and more tabs.
    * Layout and interface are still the same.

2. Unix and Git commands served hot

    * Commands are automatically injected to the `PATH` environment variable.

3. Look and feel

    * The Monokai color scheme is very appealing especially the grayish background.

**Note:** [Git for Windows][gitforwindows] is only available for the full version of the installer.
{: .notice--info}

**Pro Tip:** Just get the full version. It is really that convenient.
{: .notice}

### Conclusion

I have been using Cmder for quite some time now. In my opinion, the convenience and features that Cmder brings, makes it the best free console emulator for Windows.

Cheers!

[cmder]: http://cmder.net/
[osx]: https://www.apple.com/lae/macos
[gitforwindows]: https://gitforwindows.org/
[conemu]: https://conemu.github.io/