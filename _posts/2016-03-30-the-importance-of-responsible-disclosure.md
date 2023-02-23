---
layout: post
title: "The Importance of Responsible Disclosure"
date: 2016-03-30 21:00:00 -08:00
# modified: 2014-12-24
type: post
published: true
status: publish
permalink: 
categories: []
tags: []
author:
  login: phoneboy
  email: dwelch@phoneboy.com
  display_name: Dameon Welch
image:
  feature: disclose-responsibly.jpg
  #credit: dargadgetz
  #creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
---
From [Wikipedia](https://en.wikipedia.org/wiki/Responsible_disclosure):

> Responsible disclosure is a computer security term describing a vulnerability disclosure model. It is like full disclosure, with the addition that all stakeholders agree to allow a period of time for the vulnerability to be patched before publishing the details. 

While there is a fair amount of debate over what is considered a reasonable period of time to allow this to happen, or even sometimes what constitutes a vulnerability, most people I know in the industry generally agree that responsible disclosure is a good thing overall.

The responsible disclosure process allows the software and services we rely on every day to get better and more resilient to malicious actors who regularly look to subvert these systems for their own gain. As an employee of [Check Point](http://www.checkpoint.com), I see both sides of this debate: as both a receiver of security vulnerability reports from the community and as a discloser of vulnerabilities to other organizations. 

I've been directly involved with a couple of vulnerability disclosures related to Check Point products. While I can't get into specifics, overall I believe issues are respond to quickly and appropriately. 

To speak to the other side, Check Point does find and disclose vulnerabilities in third party products as part of its ongoing security research. Some recent examples include:

* Issues in Wordpress Core involving [privilege escalation](http://blog.checkpoint.com/2015/08/04/wordpress-vulnerabilities-1/), [SQL Injection](http://blog.checkpoint.com/2015/08/11/finding-vulnerabilities-in-core-wordpress-a-bug-hunters-trilogy-part-ii-supremacy/), and [page generation](http://blog.checkpoint.com/2015/09/15/finding-vulnerabilities-in-core-wordpress-a-bug-hunters-trilogy-part-iii-ultimatum/) -- patched in WordPress 4.3.1 and above
* ["MaliciousCard" Vulnerabilities in WhatsApp](http://blog.checkpoint.com/2015/09/08/whatsapp-maliciouscard-vulnerabilities-allowed-attackers-to-compromise-hundreds-of-millions-of-whatsapp-users/) which allowed remote code execution on victim computers
* [A privacy issue in iOS versions prior to 9.0](http://blog.checkpoint.com/2015/10/01/ios-core-application-design-flaw-may-expose-apple-id-credentials/) whereby user credentials could be exposed on devices where the end user has logged out of their Apple ID on the device -- it should be noted this was disclosed to Apple 8 months prior to the release of iOS 9.

Check Point's research includes products that compete with Check Point in the marketplace. The latest example is a [complete block bypass in Cisco Firepower](https://tools.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-20160330-fp). You can see a proof of concept video here: 

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/pneyQQEiDH4" frameborder="0" allowfullscreen></iframe></center>

As noted at the beginning of the video, the disclosure of this issue happened back in November 2015 and was remediated by Cisco today (30 March 2016), 134 days after it was initially disclosed. Nothing was disclosed publicly by Check Point until this date. Check Point worked closely with Cisco PSIRT, who was cooperative and professional throughout the entire process.

While there may be some competitive benefit to this research into competitive products, it really speaks more to the fact Check Point wants to see better security for *everyone*, not just those who happen to be Check Point customers. I think Mahatma Gandhi said it best:

> "The best propaganda is not pamphleteering, but for each one of us to try to live the life we would have the world live."

Check Point is leading the responsible disclosure debate by example here. It's one of the things that makes me proud to work for Check Point.