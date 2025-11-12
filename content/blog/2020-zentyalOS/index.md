---
slug: domain-services-with-zentyalos
title: Domain Services with Zentyal OS
description: ""
date: 2020-10-18 00:00:00+0000
image: ""
tags: 
    - homelab
    - blogtober2020
---

While building out the new Intmod NUC lab, I needed to decide on how I was going to handle typical Domain services for it. I just need a basic setup to allow me to properly setup my vSphere lab. The first route of course would be spinning up a Windows domain controller and all the fixins; either by using the trial ISOs and having to rebuild  the domain every 180 days or so, or by shelling out the cash for a license. I really didn’t like either option for my current needs.  1 could be solved by spending time to write some PorwerShell build scripts and the other was just additional money  I didn’t want to spend right now.

![](zentyal.png)

While i was deciding which route to go with I remembered coming across a Linux distribution a few years ago that was designed to be an alternative to Windows domain controllers.  After some searching around I re-found  Zentryal (specifically the Development Edition which is free to use). Based off of Ubuntu Server 18.04.4 LTS,  Zentyal can serve as your domain controller, mail server, certificate authority and more.

## Setup

Getting it installed was pretty straight forward, the only catch being that the “Easy Installer” in Workstation for Ubuntu doesn’t play nice with the Zentyal installer. After getting passed that and using the default options for install, I was presented with a guided wizard that walked me through picking server roles and configuring them.  For my lab setup i just needed the basics so i setup:

- Directory Services
- DNS
- Certificate Authority

the Zentyal setup then auto selected a few other roles that were dependencies of what i selected, and ran through installing and configuring each.

![](zentyal_setup.png)

## Usage

Once Zentyal is setup, you no longer have to access the VM and can access all the functions of the server via its web console. The UI is for the most part usable. There are a few things that I would like to see cleaner but it gets the job done. There is a bit of a learning curve to the web console that I still miss from time to time. Most (but not all ) times you make a change, you need to remember to click SAVE in the upper right hand side Until you do the changes won’t be active and will just site pending on the server.  This gets me the most when setting up DNS entries, probably because you already click OK a few times as part of the process but nothing counts unless you click SAVE.

![](zentyal_dash.png)

Creating users accounts, groups, DNS entries, and certificates are all pretty straight forward. However users looking for more then just the basics may not be satisfied. Things like managed service accounts, or uploading CSRs for certificates requests do not currently exist to my knowledge. Not a big deal for a lab but I’m sure their are some out there that would want these. I honestly can’t day anything for the DNS/Firewall/Networking components, I have only setup a few DNS records for my lab so far and all the other defaults work for me currently.

One bit I have yet to be setup is having more then one domain controller.  When I build the 2nd and try to join the existing domain the join fails.  This could just take some more tinkering and learning on my part but it doesn’t seem to be as straight forward as I thought it would be.

## Conclusion

For the time being Zentyal is exactly what I wanted for my home lab, a non-expiring, simple to setup, server that hosts the basic domain services i need to setup my vSphere lab. However, my I do want my home lab to be a learning platform for  I would come across in an Enterprise settings. So eventually I probably will replace the Zentyal OS with Microsoft domain controllers (or even just Azure AD) but for now I can give a recommendation to anyone looking for a quick and dirty domain setup for small to medium labs.
