---
layout: post
title: "Why Check Point Security Management Is Still The Gold Standard"
date: 2016-03-29 21:00:00 -08:00
# modified: 2014-12-24
type: post
published: true
status: draft
permalink: 
categories: []
tags: []
author:
  login: phoneboy
  email: dwelch@phoneboy.com
  display_name: Dameon Welch-Abernathy
image:
  feature: fw1.gif
  #credit: HTTP Evader
  #creditlink: http://noxxi.de/research/http-evader.html
---
In a customer meeting, one of my colleagues was telling a customer how the central management capabilities of Check Point Security Gateways is lightyears ahead of what any other vendor provides for their products and has been for as long as I've been supporting Check Point products--20 years now! This is not just my opinion, but it is consistently stated by Gartner in their Magic Quadrant reports for Enterprise Metwork Firewalls, where Check Point has been named a Leader *since 1997*. 

The question one might ask: how come after all these years, no one has been able to seriously challenge Check Point's management capabilities? Sure, other vendors offer centralized management, but no one can operate at the same scale. A single Check Point Multi-Domain Management installation can potentially manage hundreds and thousands of gateways, where competitors struggle managing tens or hundreds of gateways. 

To me, the answer is very simple: it's in Check Point's DNA and it goes back to the very first versions of the product. 

The first version of FireWall-1 I used was 2.0. At that point, it was managed using an OpenLook GUI on SunOS or Solaris. In version 2.1, a Windows-based client was added, which has seen numerous enhancements over the years and will see [a massive overhaul](http://blog.checkpoint.com/2016/03/01/announcing-r80-security-management/) when R80 Security Management ships.

The separation of management from the firewall? That goes back to version 1, released in 1994. 

**Disclaimer**: As noted above, my employer [Check Point Software Technologies](https://www.checkpoint.com) has a dog in this hunt with their [SandBlast Zero-Day Protection](http://www.checkpoint.com/products-solutions/zero-day-protection/index.html) offering. These thoughts, however, are my own. 