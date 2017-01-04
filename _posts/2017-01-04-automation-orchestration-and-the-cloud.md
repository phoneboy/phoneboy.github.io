---
layout: post
title: "Automation, Orchestration, and The Cloud"
date: 2017-01-04 12:00:00 -08:00
# modified: 2014-12-24
type: post
published: true
status: published
permalink: 
categories: []
tags: []
author:
  login: phoneboy
  email: dwelch@phoneboy.com
  display_name: Dameon Welch-Abernathy
#redirect_from:
#  - /2016/06/05/good-password-hygiene-key-to-protecting-social-media-accounts/
image:
  feature: princess-bride.jpg
  #credit: speedygroundhog
  #creditlink: https://www.flickr.com/photos/speedygroundhog/
---
A while ago, I posted the following as a somewhat cryptic message on Twitter and LinkedIn:

<center>
<img src="/images/tweet-clear-skies-ahead.png">
</center>

To give this tweet a little more context, I'll reference [a previous post about the cloud](/2016/04/28/the-great-cloud-migration-existential-threat-or-opportunity/), where I said the following:

> In the cloud, infrastructure and applications can come and go with the push of a button. Need another 10 webservers? Done. Need to burst to handle three times the traffic? No problem. Sure, you’ve got to have physical machines to run on, but racking and stacking that stuff is easy. The physical topology? Flat. The virtual topology? Changes every second.
>
> If you’re not treating your “cloud” infrastructure in an automated fashion, you’re doing it wrong. You’re also doomed to make the same mistakes and more that you’re making today. While some of the same tools can be used in the cloud, they integrate a bit differently. There are also a number of additional considerations that must be made for cloud—considerations that, quite frankly, are very different from physical networks.

I did get something wrong in the above statement, and it's a mistake that a lot of people make. Instead of saying "automated fashion" I should have said "orchestrated fashion." The reason is simple: while automation and orchestration are related, they are not the same thing.

Automation is something good sysadmins have been doing for 30+ years. Instead of doing a repetitive task over and over again, where you are bound to make mistakes, you build a script to do the hard work for you. If you're clever, you might also create a system to execute that script on a number of systems. I actually worked on a system that did this back in the early 90s. [Chef](https://www.chef.io/) is a more modern version of the framework we built using shell scripts and rsh (this was pre-SSH).

The key thing about automation is you still have to know how to do whatever it is you're trying to do and the order in which those commands should be run. You have to be able to handle all the various error conditions and the like as well. 

Orchestration is a level above automation, it's about the intent. Automation is leveraged to bring that intent to life, but orchestration is less concerned with *how* the result is achieved, only that it is.

## What Does Automation and Orchestration Have To Do With The Cloud?

Everything.

Automation and orchestration is what gives the cloud its magical properties. Automation makes it possible to build an entire application stack with the security you specify in seconds, orchestration tells the system when and where to spin it up. Orchestration is also able to monitor the application stack for load and spin up more capacity as required, with all the necessary steps automated so it happens.

Which means, if all your doing is taking your existing manually deployed applications and businesses processes and move them on AWS or Azure, all your doing is using someone else's computer. You are gaining little to no benefit of the inherent automation and orchestration frameworks built into AWS or Azure. 

By the way, the same thing goes for your VMware, Openstack, or other similar privately hosted environments. You might gain some benefit from the consolidation of hardware, but you will gain none of the agility and have to adjust to growing complexity.

Embracing automation and orchestration in a cloud environment (public and private) does require relearning some tasks. Some of the fundamental assumptions that underlie networking are a bit different. Which means you may not be able to deploy things the same way as you did in the past, but that's ok. Not every component of every traditionally deployed application is necessarily automation and orchestration friendly. 

The good news is that automation and orchestration can improve security by ensuring everything is deployed in it's most secure manner by default, which includes using the most up-to-date components. It can also deploy full next generation threat prevention with [Check Point vSEC](https://www.checkpoint.com/products-solutions/vsec-cloud-security/) or other, similar tools. 

Patching? Upgrading? Who does that in the cloud? You just redeploy your apps with the new versions automatically. If it fails for some reason, you can easily put the old versions back in.
 
By the way, those Software as a Service applications you and everyone else uses? They're built this way, all with automation and orchestration on the backend to make it "just work." When your executives tell you to "move to the cloud," this is what they really want: services that just work. 

Many IT organizations have not delivered on this vision. This includes ones that have supposedly moved to the cloud. Because without automation and orchestration, the cloud is just another computer. 

**Disclaimer**: My employer, [Check Point Software Technologies](https://www.checkpoint.com), is always trying to stay one step ahead of the threats, even in the cloud. The above thoughts are my own.