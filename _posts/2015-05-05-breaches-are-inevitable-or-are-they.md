---
layout: post
title: Breaches Are Inevitable, Or Are They?
date: 2015-05-05 10:11:10 -08:00
type: post
published: true
status: publish
permalink: /2015/05/05/breaches-are-inevitable-or-are-they/
categories: []
tags: []
author:
  login: phoneboy
  email: dwelch@phoneboy.com
  display_name: Dameon Welch
---
From [Palo Alto CEO: Beware the Internet of Things – and watch your car](http://www.networkworld.com/article/2917859/network-security/palo-alto-ceo-beware-the-internet-of-things-and-watch-your-car.html):

> Meanwhile, corporate network security is already facing stiff challenges that have many experts saying that breaches are inevitable – something [Palo Alto Networks CEO Mark] McLaughlin isn’t willing to concede.
> 
> “It’s as if you and I would go home tonight and say to our families, ‘Somebody is going to break into the house, probably every night. They’re going to walk around, they may take stuff, take whatever they want, but they’re coming in any time they want to every day of the week, and there’s really nothing we can do about that, so we just have to be OK with that,’” he says. “Nobody’s OK with that. That’s sort of the equivalent.”

We can argue whether or not breaches are inevitable all day long. The real question is: when a breach happens, will you be ready?

People who espouse the "assume breach" mindset aren't saying to be OK with it. What they're saying is to make sure critical assets are protected and that when a breach occurs, the means are present to be alerted to it and contain it.

The reality is, many organizations aren't adequately prepared for a breach and may not even know they've been breached.

What I regularly see in my customer engagements are flat networks beyond the perimeter and DMZ segments with no security controls in place between internal segments. The reflects the mindset that security devices will block 100% of all attacks, not letting anything malicious slip through. Which is a bit optimistic, and does not account for attacks that might not even go through the gateway.

In an "assume breach" mindset, you would design your network a bit differently, isolating user workstations from servers hosting critical applications with an enforcement point in the middle applying a strict access policy. The application servers themselves might be further segmented behind enforcement points of their own to make sure applications don't unnecessarily talk to one another. The end user machines themselves would also have additional controls on them to provide protection when they are off network (as is often the case with laptops) and to protect data. All of this would be centrally managed all with appropriate logging, reporting, and alerting across the security infrastructure. 

With all the enforcement points in place with a well designed policy, breaches, if they ever happen, can be spotted and contained quickly. With the addition of other security controls, further granularity of access control can be achieved.

If you don't even know what your critical assets are, who should have access to them, have the ability to apply any sort of access policy, and report on activities (allowed or otherwise), you've got far bigger issues than any single security tool can solve.
