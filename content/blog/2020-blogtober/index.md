---
slug: blogtober2020-homelab
title: Blogtober 2020 + Homelab
description: ""
date: 2020-10-03 00:00:00+0000
image: ""
tags:
    - homelab
    - blogtober2020
---
2020 has been a weird year to say the least, with several ups and downs. Like so many others, thanks to quarantine I found myself with even more time to myself at home then I already spent. Early on I told myself that i wanted to get X and Y done, do more of Z, etc. etc.  but nearly 7 months in I have found it very hard to accomplish much.  More recently I have started to find the motivation to push myself more and more and I am excited to share 2 small bits that I am working on.

## Blogtober 2020

I want to blog more. I started this blog over 5 years ago, and have yet to find any sort of cadence I can hold myself to. So, when I saw Matt Heldstab (@mattheldstab) sending out this call for Blogtober during this year’s VMworld I decided I wanted to attempt to hold myself to the 5 posts during the month of October.  So I started on this post and ideas for the other 4. Fingers crossed I manage to hit ‘Publish’ on all of them.

## Intmod.lab 1.0

 Earlier on this year, I also decided I wanted to finally setup a lab in which I can work on improving my technical skill sets. Past attempts at this never quite got where I wanted them to and my main limitation being an apartment dweller was always the space that some 2nd (or 3rd) hand servers would take up. So when i saw William Lam from virtuallyGhetto posting about the 10th Gen i7 NUCs and saw they got up to 6 core/12 thread now, I knew I had found a solution that could work.  So over a few months I gathered up:

- 3 x Intel NUC10i7FNH
- 6 x 32gb Samsung SODIMM memory
- 3 x 2TB Crucial MX500 SATA SSD
- 3 x 500GB Samsung 970 EVO NVME SSD (after finding out the Crucial P2 ones don’'t yet play nice with ESXi)
- 3 x Vantec USB 3.0 Dual Gigabit USB Network Adapter

  Once i got the first NUC with its needed bits in, I set to work learning how to setup ESXi with the extra needed custom installs needed to handle the 10th Gen NUCs built in NIC and the USB one as well.  After a few weekends of attempts and reading blogs i manged to get it setup correctly and later on in the summer had all 3 up and going in a VSAN clusters. (with a few re-builds needed along the way). I am also trying to use Zentyal OS as my domain services server instead of using a trial copy of Windows Server that needs regular rebuilding. My hope is that a few entries for this years Blogtober will be on the next steps I take with this lab, to help me push towards both my goals.
