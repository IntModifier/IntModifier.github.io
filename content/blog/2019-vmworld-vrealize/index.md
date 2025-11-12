---
slug: vrealize-at-vmworld-us-2019
title: vRealize at VMworld US 2019
description: ""
date: 2019-09-08 00:00:00+0000
image: ""
tags:
    - vmworld
---
It is that time of year again, with each VMworld we get new announcements for the vRealize Suite Cloud Management tools. This year, there is a common thread across most of them, supporting more Public Clouds and Kubernetes support, but if you listed to this year’s keynote that will likely not come as a surprise. We are also getting some pretty big updates in a few of the products as well, especially in the area of vRealize Automation.  I have tried to break down a summary for each product for now and hope to dive deeper into each as we get more information close to the time they get GA’d.

## vRealize Operations 8.0

As I shared in my last post, vROPS 8.0 was announced bringing in many additional features, mostly focused on VMware’s goal to support the “any clod” part of its “Any App, Any Cloud, Any Device” vision.  For more details you can read my announcement post here:  <https://www.intelligencemodifier.com/blog/2019/8/19/announcing-vrealize-operations-80>

## vRealize Automation 8.0

### Entirely New Appliance Architecture

It has been a long time rumored but vRA 8 finally contains the overhaul to application architecture. Each appliance will now be a self-contained Kubernetes Pod in which each function of vRA will run in its own group of containers. Sitting through the “Evolving vRealize Automation (HBO1323BU)” session at VMworld, its sounds like the “typical enterprise deployment” is planned to be 3 appliances, that’s it. In order to handle more workflows, you just give more resources to each Virtual Appliance, and the resources will get spread out as needed to the worker groups. This also means, NO MORE WINDOWS BASED IaaS SERVERS.

![ ](vra8_arch.png)

### Application Overhaul

If you have been using vRA for some time, get ready for some big changes. With 8.0 we will finally see all the new features and functionality beamed down from the vRealize Automation Cloud (formally CAS) product into our local data centers. Some of the big changes are

- Fully New HTML 5 interface
- Ability to edit the YAML behind a blueprint right in the editing canvas
- Ability to version control your blueprints
- Action Based Extensibility (ABX) - node.js or Python scripts that can be used expand your workflows.
- vIDM services will be handled by an external Workspace ONE Access appliance
- And so much more!

This one personally has me really excited and I cannot wait to get my hands on the GA’d bits to start working with it.  In the meantime, if you are curious on what this version be like, you can check out the Hands-on Lab HOL-2002-03-CMP which is a Getting Started lab for vRealize Automation Cloud.

## vRealize Suite Life-cycle Manager 8.0

Next up, jumping from version 2.1 to 8.0 we shouldn’t be surprised that vRSLCM has also gotten quite the re-work again. While details are still a bit sparse, we do know that the UI is getting another large overhaul. There will also be an area of the UI referred to as the “Locker”, which seems to be where you will manage passwords, certificates and licenses according to early screenshots.

Also, vRSLCM will no longer be an optional part of your management cluster. Right now, it is being listed as the only way to deploy vRealize Automation 8.0. It is also looking to be what might be the suggested method to deploy the Workspace ONE Access appliance that will act as authentication point for all the new vRealize Suite tools.

## vRealize Network Insight 5.0

 With the 5.0 release there seems to be 3 main new features being added.  First VMware is adding Support for  NSX SD-WAN (VeloCould).  In demo’s I have seen, this allows your team to have visibility into Flows and Application health for traffic flowing between your VeloCoud sites. Next, they are adding native Kubernetes support. Allowing you to see the traffic in and out of your clusters and even down to the Pod and Service levels of each. Last but not least, in their ever forward moving push to support “Any Cloud” vRNI will now support Azure networks in the same way it already supports AWS and VMware Cloud on AWS.

## Product Name Alignment

Sometimes, it’s the small things that make a large difference. As part of the slew of new vRealize goodness, VMware announced a alignment of product naming between their SaaS offerings and the more traditional “on-prem” offerings!

1. Cloud Automation  Services (CAS) is now vRealize Automation Cloud
2. Log Intelligence is now vRealize Log Insight Cloud
3. Network Insight is now vRealize Network Insight Cloud
4. They also announced the upcoming vRealize Operations Cloud

![ ](vRCloud.png)
