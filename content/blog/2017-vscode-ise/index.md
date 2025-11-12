---
slug: new-ise-visualstudiocode
title: The New ISE - Visual Studio Code
description: ""
date: 2017-12-22 00:00:00+0000
image: ""
tags:
    - powershell
---
Back around late 2013 when i started looking at PowerShell, I was a Help Desk agent and just looking to save some time on calls, maybe a faster way to look up user accounts then the hardly ever improved Active Directory Users and Computers UI. Soon however, with ample help from co-workers, I started to look at using scripting to improve our imaging process for laptops/desktops. To remove manual steps that just wasted our time.  This meant i needed a new tool, I needed to be ale setup logic flows with IF/ELSE or read in parameters such as Service Tag number among other things.  So started my journey to find a Power Shell script editor.

The choice of which script editor to use is never easy when your starting your journey to learn PowerShell. Every PowerShell user that has come before you has their favorite and probably at least one they feel is equivalent to a dumpster fire. Eventually however you make a choice, because you get beyond running single commands in a standard PS shell.

At the time, from what i remember, the 2 main choices among my coworkers were the native PowerShell ISE that comes with the Windows OS and PowerGUI (which as of writing this seems to have been lost in the spin-off Dell performed of the QUEST software in 2016). The ISE is a great starting point, it is already installed if you have PowerShell, there is very little setup needed and it just works. PowerGUI had a few nice features, like a debugging mode that I personally was never ever able to replicate inside the ISE that allowed me to step through my script and see how variables fill in to help spot logic issues.

From 2014 until probably early this year mostly stuck to the ISE. As much as I enjoyed some features of PowerGUI it was very slow loading, and Dell seemed more than happy to let it die on the vine, never providing updates. I had a quick fling with PowerShell Studio, while i was designing a wrapper for the Microsoft User State Migration Tool, for my last job and in my current role i haven't had a need for a UI designer for PowerShell. However, there was a new challenger approaching, and it was going to change a lot of what I wanted from my scripting editor.

## Enter Visual Studio Code by the "new" Microsoft

In early 2016, Microsoft release .Net Core. An free to use, open-source, cross-platform  version of the .Net framework that had for so long been a Windows only thing. A few months later the next open-source project dropped from Microsoft, Visual Studio Code.  With this, Microsoft was taking the core script editor from a product they get ALOT of money for and making it another free, open-source, cross-platform  product. I downloaded one of the earlier builds and saw potential, but between my skill-set at the time and how green the product was I just couldn't make the jump and sacrifice the speed and ease i could work with ISE.

I continued to use the ISE, and it turned out the team behind VSC were working very hard at refining this new tool of theirs. In late November-December 2016 VSC came up again at work. I don't really remember how, but upon looking into it again we found that it had changed quite a bit i some wonderful ways. The user experience had been improved,  An array of plugins were available to bring things like Intellisense, and other beloved tools from the ISE over to this new editor.

It didn't happen right away, but VSC has now all but replaced ISE in our team (for the most part). I think it quickly showed its true strength, not being a piece of the Operating System.  The ISE is still very strong, mainly because as a Windows server admin, i would be hard pressed to login to a system without the ISE right there. Which if i need to tweak a script quick that lives on a service for a scheduled task is awesome.  However, because of how it was integrated at the OS level you would rarely, if ever get updates for it.  Visual Studio Code being a separate application, and being so open meant that in the year that I have been using it, features have been rolling in month by month (faster if you are part of the Insiders build ring from Microsoft).

Several of the "must install" plugins from when I started using it simply don't exist any more, because the VSC team baked those very helpful features into the program. The native Git support (after installing the Git framework separately) allowed our team to quickly move into have a code repository. For those less familiar with PowerShell, Intellisense is baked in, and it also has PSScriptAnalyzer, a best practices analyzer, built in as well which means this editor can help you learn. The best part being that the number of settings you can tweak throughout and the frequent updates and vast add-on library this editor evolves with you as your skills increase. You can even set your space vs tab preference or decide if your starting curly bracket "{" goes on the current line you are one or on a new line... but those are wars for another day.

Its not perfect, but it improves with every build (well except for the whole icon color issue of October 2017: <https://code.visualstudio.com/blogs/2017/10/24/theicon>) and I think its worth giving a shot no matter what skill level you are at with PowerShell or some other scripting language.

Visual Studio Code on GitHub: <https://github.com/Microsoft/vscode>

Microsoft product page and download links: <https://code.visualstudio.com/>

*_Release Dates are based of the product's Wikipedia entries or other Google-Fu, i apologize if they are not 100% accurate_
