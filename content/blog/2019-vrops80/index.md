---
slug: vrops8-annouced
title: Announcing vRealize Operations 8.0
description: ""
date: 2019-08-26 00:00:00+0000
image: ""
tags:
    - vmworld
---
Today during VMworld 2019, the next version of vRealize Operations Manager was announced.  Version 8.0 focuses on improving many existing features and adding several new features especially in the area of Hybrid and Multi Cloud support. Here are some highlights of the new features you can expect when vRealize Operations Manager 8.0 drops later this year

## Core Platform Updates

- More powerful Self-Driving operations leveraging Machine Learning
- More What-If Analysis Scenarios including Hyper Converged Infrastructure and Data-center Comparison
- Troubleshooting Workbench – Correlate information in one dashboard to help track down root cause of issues. You can even have multiple Troubleshooting Workbenches setup at once to help on multiple issues.
- Continuous Availability Custer Mode – Spreading your vRealize Operations Nodes across multiple sites/fault domains to help assure cluster availability

## Updated Costing Tools

Starting with version 6.7 VMware has started implementing cost analysis into the vROPS platform. Now with 8.0, they are adding many improvements and bringing vROPS closer (if not at) feature parity with the vRealize Business for Cloud offering.  

- Integration with vRealize Automation  - vROPS will now be able to provide Day 0 and Day 2 costing  information as part of vRealize Automation workflows.  Previously only some of this information could be obtained via vRBC.
- Ability to customize costs per data-center.  VMware acknowledges that not all your data-centers cost the same to run. So starting in 8.0 you will be able to enter custom costing for each data-center connected to vROPS if needed .
- Depreciation Metrics – You can now take into account for Depreciation of value for hardware over the span of its life in your environment.

## Multi-Cloud Support

- New Management Packs for Cloud Services
  - Azure
  - VMware CloudHealth
- Costing Management Pack for VMware Cloud on AWS – pull in your costing data from you VMCoAWS portal.
- Support for Day 2 workload optimization within VMware Cloud on AWS.

## Application Monitoring

- 20 new applications and services available to monitor
- Inclusion of Custom Script monitoring

## Service Discovery Management Pack now part core product

- Connects to Guest VM via VMWare Tools agent (version 10.2 or higher)
- Still requires Guest OS credentials to access
- 8.0 will ship with 41 known services out of box
- Ability to add new services to monitoring white list
- No extra agent needed for one-time script execution such as ‘Get Top-N services

## Additional Compliance Related Features

- New Compliance Rules and workflows Out of Box, including support for VMware Cloud on AWS

- Ability to Import and Export custom compliance standards

VMware Announcement: <https://blogs.vmware.com/management/2019/08/whats-new-in-vrealize-operations-8-0.html>
