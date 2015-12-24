---
layout: post
title: Palo Alto Networks Is Evading The Truth
date: 2015-12-24 13:40:00 -08:00
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
  display_name: Dameon Welch-Abernathy
image:
  feature: swiss_cheese_zaelkrie.jpg
  credit: Zaelkrie
  creditlink: http://zaelkrie.deviantart.com/art/Swiss-Cheese-332980629
---
Here’s a summary from [A Letter to Palo Alto Networks Employees and Customers](https://www.linkedin.com/pulse/letter-palo-alto-networks-employees-customers-moti-sagey-%D7%9E%D7%95%D7%98%D7%99-%D7%A9%D7%92%D7%99%D7%90?published=t):

* Vulnerabilities in several intrusion detection products were reported by The SANS Institute 3 years ago in a white paper called [Beating the IPS](https://www.sans.org/reading-room/whitepapers/intrusion/beating-ips-34137), including those sold by Palo Alto Networks.
* A few weeks ago, NetSecVulns published a video showing Palo Alto Networks gateways are still susceptible to these flaws. (Note: This video is now private)
* Rather than acknowledge the issue, Palo Alto Networks had their representatives send out emails to their customers claiming Check Point was cheating and misleading about the issue.
* After providing a test bed demonstrating the vulnerability in action to Palo Alto Networks, a representative finally acknowledged the issue and promised to develop a fix.
* Claims from Palo Alto Networks representatives that Check Point is cheating and misleading about the issue continue, despite receiving concrete proof to the contrary.

The issue is a little more nuanced than this of course, so [I recommend reading the piece by Moti Sagey on LinkedIn](https://www.linkedin.com/pulse/letter-palo-alto-networks-employees-customers-moti-sagey-%D7%9E%D7%95%D7%98%D7%99-%D7%A9%D7%92%D7%99%D7%90?published=t). That said, I have a couple questions of my own:

1. Previously unknown long-time vulnerabilities such as [those recently discovered in some of Juniper's legacy products](https://www.techdirt.com/articles/20151219/07481133129/us-govt-agencies-freak-out-over-juniper-backdoor-perhaps-theyll-now-realize-why-backdoors-are-mistake.shtml) are one thing. How can a company sit on widely reported security issues for three years and not do anything to fix them or even publicly acknowledge them? We can argue about the length of time that is acceptable per responsible disclosure guidelines, or whether the issue was responsibly disclosed in this case. I've yet to find any information security professional who thinks three years is reasonable, particularly when the issues are this widely known.
2. How can a company require [so many manual steps](https://www.paloaltonetworks.com/documentation/61/pan-os/pan-os/threat-prevention/best-practices-for-securing-your-network-from-layer-4-and-layer-7-evasions.html) to configure their security gateways to be resilient against evasions? Imagine having to perform these steps on firewalls across your enterprise, not to mention tracking continued compliance with these best practices. 
3. If this hasn’t been an issue all along, how come there is no public statement from Palo Alto Networks like there was for the [Firestorm](http://www.bugsec.com/news/firestorm/) issue? Which is, by the way, still a potential issue, but PAN [at least responded](http://researchcenter.paloaltonetworks.com/2015/12/some-clarifications-and-commentary-on-network-security-and-covert-channels/) saying they don’t believe it is.  
4. If you received—or worse, had to deliver—the communication from Palo Alto Networks about this Evader issue that has been *proven false*, how does that make you feel about Palo Alto Networks as an organization?

**Disclaimer**: I don’t know what Check Point’s formal stance on this issue is, I didn’t ask. These are my own thoughts. 

