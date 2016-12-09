---
layout: post
title: "Networks Without Borders"
date: 2016-12-08 16:00:00 -08:00
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
  feature: borderless-network.png
  #credit: speedygroundhog
  #creditlink: https://www.flickr.com/photos/speedygroundhog/
---
​​I've spent the better part of twenty years focusing on network security. That wasn't what I started out to do in my life, I was just sort of there and the industry grew up around me. I now see a day where network security is the exception rather than the rule.

Twenty years ago, people were using a few apps mostly hosted onsite from a few, wired locations. Most of the communications were not encrypted to boot. This made it practical to use a perimeter security devices to restrict who could go where and monitor the flow of data.

These days, networks are abundant and broadband. Users have multiple devices to connect across multiple networks, few of which go through some sort of perimeter security device you can control. Communications are plentiful with an increasing percentage of them encrypted. The applications used are also plentiful and increasingly hosted in the cloud, i.e. on someone else's infrastructure.

In new organizations where Software and/or Infrastructure as a Service, the traditional perimeter gateway serves almost no purpose. There's nothing in the network to segment and there little you can do in the network to protect.

To be clear, the traditional perimeter is not going away anytime soon for many organizations. There's far too much legacy infrastructure that still needs protecting and a perimeter gateway may be your best bet. However, if you're only looking at security from a network perspective, you're missing out on an increasingly larger part of the picture. In the long run, visibility and security controls has to move closer to the endpoints. Not only those the end user uses, which includes traditional desktop/laptop and mobile devices, but the servers they connect to.

For cloud infrastructure hosted in VMware, OpenStack, AWS, Azure, or similar, this can be done through the use of microsegmentation, but make sure you are able to inspect traffic beyond layers 3 and 4. The good news is that Software Defined Networking technologies make it easy to apply deep inspection only to the traffic that needs it and not for all traffic. With the right solutions, the security will be enforced dynamically based on groups defined in the virtualization environment without regard to IP addresses. Also, traditional physical network security controls can make use of this information to make more intellegent enforcement decisions!

For Software as a Service offerings, you may need to utilize something like a cloud access security broker (CASB), a software tool or service that sits between an organization's on-premises infrastructure and a cloud provider's infrastructure. A CASB allow you to integrate familiar security controls with SaaS applications to extend visibility and enforcement of security policy beyond on premise infrastructure.

On endpoints, it's simply not enough to employ regular anti-virus anymore, but tools that can block zero-day threats, which can enter a system usually through a web browser, email, or USB. Some vendors offer solutions to this that use highly instrumented solutions similar to [Microsoft EMET](https://support.microsoft.com/en-us/kb/2458544) or on-endpoint virtualization, which of course adds load to endpoints that probably already have too many agents installed. Keeping the protection lightweight and effective is key. 

Mobile devices have their own challenges. Mobile Device Management is a good start, but for true bring your own device models, end users may object to the controls this provides. It also does not address issues of user/corporate data segmentation or mobile-focused malware. A specific threat prevention solution for mobile threats is definitely required.

Ideally, of course, all of these solutions can be managed centrally with events correlated across them. Some centralized identity framework that supports both on-premise and cloud-based applications will also be useful. Having identity correlated with your security events is even better. 

It's a challenge, but I feel like we finally have the technology to get this security thing right, or at least better than we've been able to do in the past. It's going to take some effort to get there, along with supporting business processes and people, but I am hopeful organizations can and will get there.

**Disclaimer**: My employer, [Check Point Software Technologies](https://www.checkpoint.com), does offer solutions to some of the above challenges. The views above, however, are my own. 