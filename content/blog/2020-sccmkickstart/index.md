---
slug: sccm-patching-kickstart-script
title: SCCM Patching Kickstart Script
description: ""
date: 2020-12-02 00:00:00+0000
image: ""
tags:
    - sccm
---
## Solving Problems

A while back I had the need at my day job to help stream line our Windows Server patching process.  We had moved to using SCCM and Maintenance Windows but due to business requirements were not able to allow software updates to be installed too far ahead of time and just sit at PENDING REBOOT.

Unfortunately, SCCM  doesn’t really give you a lot of room for fine tuning, and none of the out of box options fit all our requirements. So My coworkers and I started look at various options to get around this.  After several attempts we settled on a “kick-start” script and scheduled task to be installed on needed systems.

Code can be found on my [GitHub](https://github.com/IntModifier/PowerShell/tree/master/sccm_software_update_kickstart).

## Quick Run Down

We installed the script and a scheduled task to run it over and over on the needed systems using SCCM itself. Once installed, the script runs as SYSTEM every hour and starts to check the WMI name space on the local system for any registered maintenance windows. The script currently look for any MWs coming up between 4 and 2 hours away. Once it gets within 4 hours of the next MW, it then queries the SCCM Software Center for all pending updates and then triggers the installs to start (all through WMI again).  Once it triggers patching it writes an event to the Event Log letting you know when it started patches.

As long as you have reboots blocked by your Patching/Maintenance Window rules you should be all set.

The script isn’t perfect but it was able to shave hours off outage time in some cases for us, so I wanted to put this out publicly in case it can help anyone else trim down working on the weekends.
