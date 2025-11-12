---
slug: vmworld-2019-kubernetes
title: VMworld 2019 - K is for Kubernetes
description: ""
date: 2019-09-10 00:00:00+0000
image: ""
tags:
    - vmworld
---
“Any Application, Any Cloud, Any Device” This was once again the main driving message behind all of VMworld this year. However, you could sum up a large majority of the event with one word, Kubernetes. VMware seemed to have something new related to what they refer to as ‘Cloud Native Applications’ everywhere you looked, I have tried to summarize some of the large announcements below.

## Bitnami, Pivotal and Heptio

VMware hasn’t been shy about acquisitions this past year, and several of them are directly related to enhancing their Cloud Native portfolio.  Last fall, VMware scooped up Heptio a start-up focused on professional services and supporting companies starting down the Kubernetes road. This evolved into the Essential PKS, a way for companies that need a more custom deployment for Kubernetes then what Enterprise PKS offers, while still being supported by VMware.

Jumping to spring 2019, VMware announced their acquisition of Bitnami. This addition adds specialty in the software packaging space, including of course containers. Already offering automation deployment of application stacks to AWS, Azure and Google Cloud Platform they quick slide right in line with VMware’s “Any Cloud” vision and not only could they enhance VMware’s container and Kubernetes products but possibly help re-work how VMware’s virtual appliances are built and deployed, much like the newly announced, self-contained, Kubernetes cluster based vRealize Automation 8.0 appliance.

Then a few days before VMworld, and then several times during the General Session(s), VMware announced their intention to acquire their partner in the PKS platform, Pivotal.  Enterprise PKS was VMware’s first large jump into production containers and Kubernetes. Not having any firsthand experience with PKS yet, I can only go off of what I have read but it seems that Enterprise PKS, while coming in at a premium over spinning up your own Kubernetes solution, it does a very nice job at delivering a close to Key-turn ready enterprise K8 deployment. If everything goes through and Pivotal joins the VMware fold, it will be interesting to see even tighter integration into the VMware stack can bring, especially when looking at the rest of the announcements this year.

## Project Pacific

Next we get a peek into the future of vSphere, Project Pacific. To summarize in the style of a cereal slogan from the 90s, “You got your Kubernetes in my vSphere!” Pacific represents the effort to bring Kubernetes into your datacenter as a “first class citizen.” You will be able to see, interact, and manage your K8 Clusters right from the vSphere interface. This won’t just be an add-on for vSphere, the actual framework for Kubernetes will be weaved into the foundation of vSphere.

Right now, I look at this a very good way to help any VMware customer (or future customer) bring “Cloud Native Applications” into their production environment. Also, VMware will be including their Harbor container registry as a part of this future version of vSphere. A seemingly small addition, but another step of lowering the barrier of entry into proper container and Kubernetes deployments.

Now, I will be the first to admit that my knowledge in Kubernetes is still at a point where I can’t do justice into some of the technical details on how VMware plans to make Kubernetes seamless with Project Pacific. However I can recommend that you check out the Technical Overview by Jared Rosoff  on the VMware blogs and his and Michael West’s VMworld session (HBI4500BU) up on VMworld Videos. You can also find the “Introducing Project Pacific” breakout session by Himanshu Singh and Kit Colbert (HBI4937BU) on the VMworld video site, along with checking out the Day 2 General Session for some live use case demos.

## Tanzu and Tanzu Mission Control

Another piece of the VMware Kubernetes puzzle was also announced, VMware Tanzu and  Tanzu Mission Control. Where Pacific focuses on helping you run and manage Kubernetes within vSphere, Tanzu’s focus is you with Kubernetes sprawl across multiple cloud providers. A single management console for administrators to use to manage clusters no matter where they reside, that will then translate your clicks into the proper API for that cloud provider, so you don’t have to learn any cloud specific commands.

The Day 2 General Session demos are focused around Tanzu as well, including the fictional company Tanzu Tees,  and you can also catch one of these session recordings from VMworld

- Introducing VMware Tanzu Mission Control: Manage Kubernetes at Scale (KUB1835BU)
- More Devs, No Problem: Managing Self-service Access with VMware Tanzu (KUB1851BU)
- Run Upstream Kubernetes Consistently Across Clouds with VMware Tanzu (KUB1840BU)

## Kubernetes Academy

No matter how VMware simplifies the tools needed to manage a Kubernetes cluster in production, it is still a fundamental change on how we look at applications. Which means training is still needed across IT to get everyone on the same page before architecting these next generation apps. Well VMware is determined to help here as well. Not only can you find several Hands-on-Labs on things like PKS, using NSX-T with Kubernetes, and we can assume Tanzu and Pacific after they release; but you can also take part in the new free training from Kubernetes Academy. At VMworld this year, I had an opportunity to sit through most of (busy schedule this year) an introduction  to containers and Kubernetes. Led by several employees of VMware that came over from the Heptio acquisition, they walked the group through the foundations and creating a container based web application and then combining it with a MySQL container in a Kubernetes cluster. Classes like these are what you will find at Kubernetes.Academy for free to help get everyone from development to infrastructure on the same page when it comes to tiny and mighty deployments.  

With all the Kubernetes announcements and updates it is very clear, if learning your K8s isn’t on your roadmap, it should be.
