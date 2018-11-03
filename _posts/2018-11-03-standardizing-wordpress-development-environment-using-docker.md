---
title: "Standardizing Your Wordpress Development Environment Using Docker"
excerpt: "Guide on how to quickly setup your WordPress development environment using Docker. Learn more on how Docker helped me virtualizing LEMP stack in Windows."
toc: true
toc_label: "Table of Contents"
categories:
- software
tags:
- wordpress
- web
- docker
---

## Introduction

You probably already heard of [WordPress][wordpress] or you might already been using it to power your websites or blogs. According to the report of [W3Techs][w3techs-trend], WordPress is powering *32.2%* of all websites and *59.4%* of all [content management systems][cms] across the globe as of November 2018. 

Yes, the numbers are quite big for WordPress and the community is huge. Also, there are many themes and plugins being implemented actively by the community. Are you are planning to build your own personal website? I recommend you check this platform especially if you're not a very technical person.

**Important Note:** Be cautious on the plugins you are including to your website in order not to compromise security, performance, and stability.
{: .notice--warning}

For experienced WordPress developers, do you use a separate development environment before publishing your changes to a production or live environment? If yes, How do you maintain the consistency of your development environment from the production environment? Head down below to know more about the problems I encountered and how I handled them.

## Problems

The most popular server stack for running WordPress might still be [LAMP][lamp], an acronym for Linux, Apache, MySQL/MariaDB, and PHP. Most hosting solutions provider will use Linux as the operating system for your WordPress instance. But, what if you are using Windows or Mac OS for development?

Aside from the operating system, another variable is the software package for development. Some will use [XAMPP][xampp]. Others might be using [WAMP][wamp] or [MAMP][mamp]. It is great if the team can have a consensus on what to use for uniformity. Still, the development environment wouldn't be able to be as close as the production setup.

Furthermore, what if the software stack itself will be modified? i.e. instead of using Apache, the infrastructure will shift to use [Nginx][nginx]. All of the developers will need to resetup their development environment and might encounter setup delays.

## Docker to the Rescue

[Docker][docker] is a very popular tool especially for DevOps people. It provides virtualization capabilities at the operating system level, called as *"containerization"*. It lets you create containers containing application(s) inside. For deeper details regarding Docker containers, you may visit the link [here](https://www.docker.com/resources/what-container).

Docker supports major operating systems (i.e. Linux, Windows, and Mac OS). This will help address the operating system differences not only between developers but also with the live environment. Even if the developer is running Windows, we can build containers using Linux as base. Quite handy, right?

The Docker configuration file for the development environment can be submitted to the source repository which greatly promotes portability and productivity. Team members can now just pull the project and run it instantly without setup woes.

## Dockerized WordPress

I chose [LEMP][lemp] stack as a starter project. Basically, this stack will use Nginx instead of the usual Apache web server. I listed the chosen Docker containers below for virtualizing the desired stack. Read more to find out how these components can be started with just one command using Docker Compose.

### List of Containers

- [Nginx][docker-nginx] - Web server
- [PHP-FPM with WordPress][docker-wordpress] - FastCGI implementation with built-in WordPress
- [MariaDB][docker-mariadb] - Database server

### Getting Started

1. Install Docker and Compose. Click [here][docker-install] for the official guide.

2. Clone the [docker-wordpress-lemp][docker-wordpress-lemp] Git repository.

    ```
    git clone https://github.com/edoswaldgo/docker-wordpress-lemp.git
    ```

3. Run Docker Compose

    ```
    cd docker-wordpress-lemp
    docker-compose up -d
    ```

4. Open the URL ( [http://localhost](http://localhost) ) via web browser for initial WordPress setup.

    ![image-center](/assets/img/blog/docker-wordpress/wordpress-init-setup-600x450.jpg "WordPress Initial Setup"){: .align-center}

5. Voila! Your environment is up and running.

    ![image-center](/assets/img/blog/docker-wordpress/landing-page-600x450.jpg "WordPress Landing Page"){: .align-center}

## Virtualization Alternative

Docker seems to be similar to a virtual machine. Why not just use [Vagrant][vagrant]? Short answer is familiarity. I am just more familiar with Docker as of the moment. Feel free to explore this one and may leave me messages about your experiences with Vagrant.

## Conclusion

The Dockerized setup of WordPress for me is very clean, lightweight, and convenient. My local machine need not to be cluttered by the required components. I can easily dispose the created containers without worrying about dangling files.

Virtualization is key for bridging setup gaps and differences. Keeping the development environment close to the live environment is a big plus and Docker provided this without much hassle. In fact, Docker setups can be used in production as well. But, just always remember to remove sensitive data and do not expose them in plain text for production.

If you haven't tried Docker yet, try it out now and I am pretty sure you will love it. Cheers!

**Extra:** My personal website is currently powered by [GitHub Pages][github-pages] using [Jekyll][jekyll]. You might wonder why I chose this setup and why I did not use WordPress for my personal website. Wait for my next post and we will tackle this topic soon!
{: .notice--info}


[wordpress]: https://wordpress.com/
[w3techs-trend]: https://w3techs.com/technologies/details/cm-wordpress/all/all
[cms]: https://en.wikipedia.org/wiki/Content_management_system

[lamp]: https://en.wikipedia.org/wiki/LAMP_(software_bundle)
[lemp]: https://lemp.io/
[xampp]: https://www.apachefriends.org/index.html
[mamp]: https://www.mamp.info/en/
[wamp]: http://www.wampserver.com/en/
[nginx]: https://www.nginx.com

[vagrant]: https://www.vagrantup.com
[docker]: https://www.docker.com/

[docker-nginx]: https://hub.docker.com/_/nginx/
[docker-wordpress]: https://hub.docker.com/_/wordpress/
[docker-mariadb]: https://hub.docker.com/_/mariadb/

[docker-install]: https://docs.docker.com/install/
[docker-wordpress-lemp]: https://github.com/edoswaldgo/docker-wordpress-lemp

[jekyll]: https://jekyllrb.com/
[github-pages]: https://pages.github.com/

