---
title: "Find Hard-coded String Literals via PMD"
categories:
- Software Development
tags:
- Code Review
- Java
- PMD
---

### Overview
My blog post yesterday (*Click [here][find-hardcoded-eclipse] to view*) was about finding hard-coded Java String literals via [Eclipse][eclipse]. I separated this post (*even if they are closely related*) because the post yesterday is a stand-alone solution.

This new post will focus more on the limitations and integration problems of just using the code style check of Eclipse.

### Problem
1. Not all developers use Eclipse for their development environment.
2. Developers can just ignore and bypass the fixing of hardcoded strings.
3. Easy integration with other software like [Jenkins][jenkins] / [Hudson][hudson] for [CI (*Continuous Integration*)][ci] and [SonarQube][sonarqube] for code quality monitoring.

### Solution
Many source code analyzers are available in Java and [PMD][pmd] is one of the commonly used tool. This tool can spot different kinds of code smells and it has great integration support for other software. It can be used as build breakers for enforcing developers to fix their code as early as possible.

To have a better understanding of the tool, I suggest to check the documentation of the tool as the documentation is very detailed.

I found the `AvoidDuplicateLiterals` rule in PMD and it can spot duplicate String literals, given a threshold. The threshold is defined by the `maxDuplicateLiterals` property which is set to four by default.

Sadly, my approach is not really neat because it requires the threshold to be set to zero in order to work. This setting deviates from the real purpose of avoiding "duplicates". Another approach is to create a custom PMD check for this but its code will just like be a copy of `AvoidDuplicateLiterals`.


1. Create the custom rule set for customizing *AvoidDuplicateLiterals*.

    ```xml
    <?xml version="1.0"?>
    <ruleset name="Custom ruleset"
        xmlns="http://pmd.sourceforge.net/ruleset/2.0.0"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://pmd.sourceforge.net/ruleset/2.0.0 http://pmd.sourceforge.net/ruleset_2_0_0.xsd">

      <description>
        This ruleset checks for hardcoded String literals.
      </description>

      <!-- Customize the AvoidDuplicateLiterals rule's properties -->
      <rule ref="rulesets/java/strings.xml/AvoidDuplicateLiterals">
        <properties>
            <property name="maxDuplicateLiterals" value="0"/>
            <property name="skipAnnotations" value="true"/>
        </properties>
      </rule>

    </ruleset>
    ```

2. Save the custom rule set as XML to a desired directory.
3. Go to the */bin* folder of the PMD distribution.
4. Run PMD via command-line for testing.

    ```
    pmd -R no-hardcoded-string-literal.xml -d C:\temp\HelloWorld.java -f html
    ```

    **Note:** You may execute `pmd -h` for help.
    {: .notice}

5. View the output. Below is the HTML output viewed in a web browser upon executing the command above.

**Pro Tip:** For suppressing checks, may append a `NOPMD` comment to the specific line of code.
{: .notice}

### Sample Result
![image-center](/assets/img/blog/find-string-literal-pmd.png "PMD HTML Output"){: .align-center}

PMD is a great tool and utilizing it will surely increase the code quality of developers. I'll try to post about PMD integration with a CI] tool for automated code review in the future.

[find-hardcoded-eclipse]: /blog/tips&tricks/java/eclipse/find-java-string-literal-eclipse/
[pmd]: http://pmd.sourceforge.net
[eclipse]: https://eclipse.org
[ide]: https://en.wikipedia.org/wiki/Integrated_development_environment
[sonarqube]: http://www.sonarqube.org
[jenkins]: https://jenkins-ci.org
[hudson]: http://hudson-ci.org
[ci]: https://en.wikipedia.org/wiki/Continuous_integration
