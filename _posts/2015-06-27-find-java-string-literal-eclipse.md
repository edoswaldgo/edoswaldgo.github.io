---
title: "Find Hard-coded String Literals via Eclipse"
redirect_from:
  - /blog/tips&tricks/java/eclipse/find-java-string-literal-eclipse
excerpt: "Guide on finding hard-coded strings in Java using the Eclipse IDE."
categories:
- software
tags:
- java
- eclipse
---

## Overview

As many developers know, [hard-coding][hardcoding] is a bad practice when trying to code a maintainable program. Programs need to be modified and recompiled in order for the new hard-coded value to take effect. This is also a common headache when the program needs to support i18n (*internationalization*), but the program has many hard-coded label / description.

## Problem

Provided that an individual is using [Eclipse][eclipse] for development, how can the individual find all the hard-coded string literals? Does the invidual need to create a complex regular expression in order to spot those instances?

## Solution

Fortunately, the Java compiler, implemented by Eclipse, supports some code style checks that can greatly help developers when coding. One of the code style checks is for *"Non-externalized strings"* and below are the steps for enabling this check.

1. Open the Eclipse Preferences window and find the *Errors/Warnings* subsection.
2. May enable project specific settings in case other projects need not to have these kinds of checks.
3. Change the value for *"Non-externalized strings"* to ```Warning``` or ```Error```.
4. Click OK.

    ![image-center](/assets/img/blog/find-string-literal-eclipse/eclipse-settings-string-literal.png "Eclipse Settings for String Literal"){: .align-center}

## Sample Result

After applying the settings above, the code editor in Eclipse will now add indicators to specific lines of codes that violates the *Non-externalized strings* check. Below is the sample image of the code editor with the applied settings.

![image-center](/assets/img/blog/find-string-literal-eclipse/eclipse-warning-string-literal.png "Eclipse Warning for String Literal"){: .align-center}

**Note:** If exclusion of a line is desired, the developer may append the $NON-NLS$ tag. The Eclipse Java compiler will then just ignore the hard-coded string.
{: .notice}

[hardcoding]: https://en.wikipedia.org/wiki/Hard_coding
[eclipse]: https://eclipse.org
