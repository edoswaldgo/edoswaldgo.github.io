---
title: "Offline installation of npm packages"
redirect_from:
  - /blog/tips&tricks/node.js/npm/nodejs-npm-offline
excerpt: "Guide on how to install NPM packages for Node.js using the npmbox tool."
categories:
- software
tags:
- node.js
- npm
---

## Overview

It's been awhile since the last time I posted on my blog. I've been quite busy during the past weeks and kept resting on weekends. Sorry for not being able to post and give weekly updates. Today, I'll tackle something about [Node.js][Node.js].

Node.js is rapidly gaining popularity in software development nowadays due to many reasons (may check the trend [here][node.js-trend]). One of the reasons is the usage of JavaScript for server-side. Imagine, coding the back-end and front-end using the same language.

Also, it uses a package manager named, [npm][npm]. It has a repository of JavaScript packages which are retrieved from the Internet to be used by Node.js applications.

## Problem

Not all organizations provide complete access to the Internet. Some might have intranet networks without any access to the Internet. Given this scenario, how can an individual use npm to install desired Javascript libraries?

## Solution

As the package manager of Node.js relies on an Internet connection to retrieve packages. [npmbox][npmbox] is created in order to archive online packages including their dependencies. Yes, the dependencies are included. It can greatly save us from installation headaches.

**Workstation with Internet connection:**

1. Download and install [Node.js][Node.js]. (This will automatically install `npm`)
2. Open any desired terminal / command-line client.
3. Install the npmbox package from `npm`.

    ```bash
    npm install npmbox
    ```

3. To verify that npmbox is successfully installed, may execute the commands provided by npmbox like `npmbox` and `npmunbox` directly from the command-line.

    ```bash
    npmbox --help
    npmunbox --help
    ```

4. Now, we must archive the npmbox package in order to be used by other machines without Internet connection. (It is rather strange that we are archiving the archiver.)

    ```bash
    npmbox npmbox
    ```

5. Copy the installer of Node.js and the generated file of npmbox to the workstations without Internet connection.

**Workstation without Internet connection:**

1. Install [Node.js][Node.js]. (Using the downloaded file earlier)
2. Open any desired terminal / command-line client.
3. Go to the directory having the .npmbox file.
4. Untar the .npmbox file

    ```bash
    tar -xvf yourfile.tar
    ```

5. In the same directory, a new folder named `.npmbox-cache-folder` will be generated.
6. Execute the following command in order to use the offline feature of npm for installing npmbox. (I got the command from [here][npm-offline-command].)

    ```bash
    npm install --global --cache ./.npmbox-cache --optional \
                --cache-min 999999 --fetch-retries 0 \
                --fetch-retry-factor 0 --fetch-retry-mintimeout 1 \
                --fetch-retry-maxtimeout 2 npmbox
    ```

7. Verify if npmbox is successfully installed to the machine.
8. May now install archived JavaScript packages (in `.npmbox` extension) using the `npmunbox` command.

{% capture notice-text %}
* In case error is encountered while unboxing the archived package, may check if the npmbox installed in the workstations have the same versions.
* If the npmbox versions are the same, but *online errors* are still encountered, try installing version 1.0 of npmbox.
{% endcapture %}

<div class="notice--info">
  <h4>Notes:</h4>
  {{ notice-text | markdownify }}
</div>

[node.js]: https://nodejs.org/
[npm]: https://www.npmjs.com/
[npmbox]: https://www.npmjs.com/package/npmbox
[npm-offline-command]: http://stackoverflow.com/questions/25549730/install-npmbox-on-a-windows-offline-machine
[node.js-trend]: https://blog.risingstack.com/how-google-sees-node-js/
