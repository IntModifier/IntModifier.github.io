---
slug: replaceing-vrli-node
title: Replacing a vRealize LogInsight node
description: ""
date: 2018-08-26 00:00:00+0000
image: ""
tags:
    - vmware
---
NOTE: I am not a member of VMware Global Support Services, nor should you use this as any sort of replacement for a service ticket or vmWare published documentation.  This is just a process that I had to piece together during my own support case with them wanted to document for home lab use. Attempt the below steps at your own risk.

## Problem Statement

While trying to expand storage per the VMware documentation within 2 separate vRLI 4.5 clusters, I had 1 of 3 nodes in each cluster fail to expand storage.  After a few hours with support via email and phone, and several attempts to salvage the nodes by trying to expand the storage manually, it was decided that the nodes needed to be replaced.

## TLDR

Unjoin bad node from cluster, backup the log data off the node, Delete node, build new node, join new node, restore data to appliance, load data into vRLI.

## Procedure Used

1. Remove Node from cluster via UI by following the documentation for your version of vRLI
2. Find a secondary location you can temporarily store the data. I had a utility server that i added an extra 2.3 TB drive to for this.
3. We used PSFTP to connect and move data
4. login to the 'bad' node as root  `open root@<applianceFQDN>`
5. use `lcd <destionation loc>` to set your local directory to the destination for the data you found in step 2
6. navigate to the log 'blob' on the appliance - `cd /storage/core/loginsight/cidata`
7. pull that data - `get -r store store`
8. Wait. this is probably going to take a while. I had to leave hours  running overnight.
9. When the file copy is done, validate you have the right amount in your backup location
10. I had our first copy fail to copy it all so I had to try again
11. Power down the node being replaced
12. Delete the VM
13. Redeploy a new node with the same host-name and IP address
14. Join the new node
15. via the vRLI console, place the new node into Maintenance Mode
16. Open PSFTP
17. login to the new node as root  `open root@<applianceFQDN>`
18. `lcd` back to your location for step 2. DO NOT lcd INTO the 'store' folder that was created
19. `cd /storage/core/loginsight/cidata`
20. load the data back into the appliance using `put -r store store`
21. Waiting again
22. Putty into the appliance as root
23. run `cd /storage/core/loginsight/cidata`
24. Set the correct permission son the store folder with `chmod 755 store`
25. Stop services on the node with `service LogInsight stop`
26. run the following script to load the log data into the LogInsight application: `for bucket in $(ls /storage/core/loginsight/cidata/store | grep -v 'generation\|buckets\|strata_write.lock'); do echo y | /usr/lib/loginsight/application/sbin/bucket-index add $bucket --statuses archived; done`
27. more waiting
28. start up services - `service loginsight start`
29. via the vRLI UI, bring the cluster out of maintenance mode
