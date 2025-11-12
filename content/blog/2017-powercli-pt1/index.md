---
slug: connect-viserver-part-1
title: Connect-VIServer -Part 1
description: ""
date: 2017-10-07 00:00:00+0000
image: ""
tags:
    - powercli
    - powershell
---
## Installing and Connecting

Before we get to far,you will need to have PowerCLI installed.  You can probably get away with a an older version but as of my writing this I have only validated these commands using PowerShell 5.1 and PowerCLI 6.5.x

### Prerequisites

1. Basic knowledge of PowerShell
2. Uninstall any versions older than 6.5 from the Windows Control Panel
3. Update PowerShell (WMF) 5.1 - Info Here
4. If this is your first time installing anything via Find-Module and Install-Module, you will most likely be prompted to install the Nuget module when you run the commands for the first time.

### Installing PowerCLI from the PSGallery

Starting with version 6.5, VMware has stopped delivering PowerCLI via MSI installer. They have instead embraced the more standard delivery of PowerShell Modules via Microsoft's PSGallery. This has the benefits of making the module easier to install on new computers, and easier to update when a new version is released. Also by using a more standard setup for the module, this means you no longer have to launch a special PowerCLI shell. The PowerCLI module is loaded right into the normal PowerShell window making thinks like scripts much less complicated. For users of previous versions, as mentioned above in the prerequisites, need to manually uninstall all old version as the new Install method is not capable of doing this. Now lets get installing.

1. Open a PowerShell prompt in Administrator Mode.
2. Use the following command to Find PowerCLI out on PSGallery
`Find-Module -Name vmware.powercli`
3. You should have a result like the one below:
![ ](Find-Module.png)
4. Now to install the module use the following command, which will then ask you to confirm you want to install the module from an "Untrusted Repository".

`Find-Module -Name vmware.powercli | Install-Module -AllowClobber`

![ ](Confirm+Install.png)

5. You will now see PowerShell download and install PowerCL

![ ](Installing.png)

Once the progress bars disappear, you are now ready to connect to your VMware environment via PowerCLI! Which I will cover in part 2.
