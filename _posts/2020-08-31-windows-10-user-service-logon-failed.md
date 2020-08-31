---
title: "Windows 10 User Profile Service Failed During Login - Quick Fix"
excerpt: "Have you experienced a Windows login error before that's not about an incorrect password? I ran into the User Profile Service service failed the sign-in! Check my post on how to fix it."
toc: true
toc_label: "Table of Contents"
categories:
- technology
tags:
- software
- microsoft
- windows
- win10
- guide
- troubleshooting
splash_teaser: /assets/img/blog/windows-10/win10-user-profile-service-failed-sign-in-cover-600x450.jpg
---

## Introduction

Do you perform periodical cleanups on your machine? Or do you only do it when your computer is running low on disk space?

I clean unused programs and files when I notice my computer is running low on space. It is easy for my case because I frequently open the *File Explorer* of Windows and see the disk usage.

My usual process is to check for unused programs and uninstall them. Afterwards, I use the [WinDirStat][windirstat] tool for spotting large files that take a lot of space on my disk drive.

I delete those files and folders which seem unused then my machine is good to go again. Unfortunately, I did something different which led me to a critical problem.

## Problem

A few months ago, I wanted a more organized file system for my personal and work stuff. Creating new Windows accounts was one of the good ways to have boundaries and separation.

But, when I tried logging in to the newly created Windows 10 account, I suddenly encountered the "__*The User Profile Service service failed the sign-in*__" error!

![image-center](/assets/img/blog/windows-10/win10-user-profile-service-failed-sign-in-600x450.jpg "User profile cannot be loaded"){: .align-center}

I couldn't switch to other user profiles which I knew were working before. Head down below and see how I tried to solve the problem. _*anxious*_

## Troubleshooting

I restarted and shut down my PC but same error was encountered and account switching was not available

I restarted my computer again, now in *Safe Mode*, but it still didn't solve the issue. 

Luckily, my computer had a recent snapshot and I used it for *System Restore*. Restoring my PC state to the previous snapshot let me log in to the working user account.

I ran the Windows [System File Checker][sfc] tool to check and repair any corrupted Windows file. Then, I created a new user account but the same error was replicated.

*System Restore* to the rescue again! But at that time, I searched further on the Internet for similar cases and possible solutions. I stumbled upon this Microsoft Community [thread][thread] and tried one of the suggested fixes.

I got hold of another Windows 10 machine that was still working. I copied the whole `C:/Users/Default` folder from that machine to my problematic PC.

I tried logging in to a new user account and it successfully proceeded to the Windows desktop!

## Conclusion

The cleanup I made before caused the Windows login error as I deleted the `C:/Users/Default` folder which is vital for new Windows user accounts. 

It was a great troubleshooting and learning experience. Being able to fix it was a big relief because it will be quite inconvenient to reinstall the operating system.

To end my post today, let us remember to not delete system files and/or folders especially if we don't know their purpose. *HAHAHA!* Cheers!

[windirstat]: https://windirstat.net/
[sfc]: https://support.microsoft.com/en-ph/help/929833/use-the-system-file-checker-tool-to-repair-missing-or-corrupted-system
[thread]: https://answers.microsoft.com/en-us/windows/forum/all/user-profile-service-failed-the-logon-windows-10/1d47268a-c80f-4a69-8695-c9de0a9857f2
