---
layout: post
title: "The Great Cloud Migration: Existential Threat or Opportunity?"
date: 2016-04-28 17:00:00 -07:00
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
image:
  feature: stormfront.jpg
  credit: Craig Morey
  creditlink: https://www.flickr.com/photos/pixelthing/
---
As part of my day job at Check Point, I review customer security architectures and make recommendations with an eye towards securing the right things the right way. Generally, the customers I talk to have a pretty good idea of what they have, how it’s laid out, and what controls are in place. I can usually find gaps in their knowledge, as well as their controls, but at least there is some basic knowledge of their own environment.

Recently, I was asked if we could help a customer inventory their security equipment because they quite simply don’t know what they have. How can you protect the right things the right way when you don’t know what those things are and what tools you have to do it?

One thing that is typically done as part of my engagements is a [Security CheckUp](https://www.checkpoint.com/resources/securitycheckup/). To perform the Security CheckUp, a Check Point appliance is put onto a span port in the customer network so traffic can be passively analyzed. After some time, a report is generated ([see a sample](http://supportcontent.checkpoint.com/documentation_download?ID=13521)), which I review to get a sense for what is in the environment, what potential threats exist, and how effective certain security controls are.

The Security CheckUp won’t tell me, at least directly, what controls do exist in the environment, nor does it tell me where in the environment they are. Other vendors make tools that can map out the network, but even those tools have their limits. For example, they can’t tell you about any layer 2 equipment within the environment. It also can’t tell you about anything that might be on a span port (e.g. an IDS sensor) or equipment that is powered off, but in a rack somewhere.

Even with these tools, a fair amount of manual work is still required to turn that data into an accurate picture of what your environment is. In short, there is no “easy” button for this problem; it’s going to require real effort to track down what is where.

How can this happen? How can organizations become so unaware of what they have that they need someone to come in and tell them what they have and where it is? Then it hit me: anyone making use of “the cloud” is going to have this problem. Or they already are and they don’t know it.

In the cloud, infrastructure and applications can come and go with the push of a button. Need another 10 webservers? Done. Need to burst to handle three times the traffic? No problem. Sure, you’ve got to have physical machines to run on, but racking and stacking that stuff is easy. The physical topology? Flat. The virtual topology? Changes every second.

If you’re not treating your “cloud” infrastructure in an automated fashion, you’re doing it wrong. You’re also doomed to make the same mistakes and more that you’re making today. While some of the same tools can be used in the cloud, they integrate a bit differently. There are also a number of additional considerations that must be made for cloud—considerations that, quite frankly, are very different from physical networks.

There was a time when security people were siloed off from other parts of the organization. Security only got brought in at the end to make it all work and is often the scapegoat when it doesn’t work (or things get hacked). If we’re going to be one step ahead of the threats, this practice has to end. Security people have to be part of the conversation as applications and services are being conceived, or in the case of software as a service, being migrated to. Likewise, security people have to figure out how to stop being a business impediment, but being a [business enabler](http://phoneboy.org/2014/11/23/the-department-of-yes/).

It also means, if you're a security person not versed in the ways of infrastructure or software as a service, if you want to remain relevant, you need to bring your skills and knowledge up to scratch, and quickly.

One could look at all of this movement to cloud as a threat to your career. If everything can be automatically deployed, do we need IT or Information Security professionals anymore?

Absolutely, organizations will still need people that understand how it all connects together and how to secure it. In fact, I see this as a huge opportunity to improve security for all organizations. Because everything is fundamentally shifting, we have a chance to get this security thing right after decades of getting it wrong. This means, finally, being able to securing the right things the right way, regardless of where they may be.

It’s a huge opportunity. It’s going to require all of us to acquire new skills—both technical and political—to accomplish. The question is: do you have the courage and the vision to take advantage of it?
