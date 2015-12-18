---
layout: post
title: Shouldn't a Security Gateway Be Secure By Default?
date: 2015-12-10 08:08:04 -08:00
type: post
published: true
status: publish
permalink: /2015/12/06/marketing-hype-and-security-technology-that-actually-works/
categories: []
tags: []
author:
  login: phoneboy
  email: dwelch@phoneboy.com
  display_name: Dameon Welch-Abernathy
---
From [Palo Alto Networks: Best Practices for Securing Your Network from Layer 4 and Layer 7 Evasions](https://www.paloaltonetworks.com/documentation/61/pan-os/pan-os/threat-prevention/best-practices-for-securing-your-network-from-layer-4-and-layer-7-evasions.html#16594): 

> To monitor and protect your network from most Layer 4 and Layer 7 attacks, here are a few recommendations

While I'm all about Best Practices documentation, one wonders why some of the items in this documentation are even required. 

> Block all unknown applications/traffic using security policy. Typically, the only applications that are classified as unknown traffic are internal or custom applications on your network, or potential threats. 

Wouldn't a better approach be to only permit the applications you want to allow rather than to block all unknown applications? Oh, wait, that's not how that product was designed to work...

> Create a zone protection profile that is configured to protect against packet-based attacks: * Remove TCP timestamps on SYN packets before the firewall forwards the packet [...] * Drop malformed packets. * Drop mismatched and overlapping TCP segments

A proper stateful firewall should do all of these things by default, shouldn't it? Same with the half dozen other checks they say to enable via the CLI?

Doesn't it seem strange to anyone else that you have to manually configure so many options to make the device more secure? What's the likelihood customers have actually deployed their gateways in this fashion? Are they getting the performance they expect if they do so? My guess: probably not. 

To add a little more fuel to the fire: [Firestorm](http://www.bugsec.com/news/firestorm/). This attack uses TCP SYN + Data packets to bypass certain firewalls. Per the article:

> We disclosed the full details of the vulnerability to major vendors affected by the flaw. One of the vendors who replied, explained that they do not see this issue as a vulnerability because, by design, their firewall permits full TCP handshake in order to inspect the application type.

They said that once their state machine proceeded beyond the TCP handshake, they would recognize the application, matching a subsequent rule that applied to application traffic. The vendor added that if there was an application they did not recognize, they would treat the session as ‘unknown-TCP’ and, again, perform an additional security policy lookup to decide whether to allow or block the traffic.

Now that this information is out there, it is only a matter of time before some develops a tool that can be used to bypass these security devices and, short of blocking all traffic, there's nothing you can do to mitigate the threat "by design." Oh wait, someone already has. (**Note**: There was a tool at https://github.com/stasvolf/SynTunnel but it has been removed)

It should be noted that [Check Point Security Gateways are not susceptible to Firestorm](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk109042). 

**Disclaimer**: While I work for Check Point Software (a competitor to Palo Alto Networks), the above thoughts are my own.
