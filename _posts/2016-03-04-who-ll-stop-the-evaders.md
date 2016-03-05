---
layout: post
title: "Who'll Stop The Evaders?"
date: 2016-03-05 21:55:00 -08:00
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
  feature: http-evader.png
  credit: HTTP Evader
  creditlink: http://noxxi.de/research/http-evader.html
---
​In the information security business, we are always trying to stay one step ahead of the threats out there. Sometimes, the threats come from our own misconfigurations or lack of security controls, other times it comes from pushing the boundaries of what is acceptable in a given protocol allowed through a security control, eliciting a specific reaction which allows a hacker to obtain their objective (namely, getting a foothold in your environment).

The [HTTP Evader](http://noxxi.de/research/http-evader.html) test suite demonstrates techniques that can be used to bypass detection by various inline security tools. Specifically it uses HTTP in unique ways to obfuscate malicious code so it can not be detected by a security gateway. The "malicious" code, in this case, is the EICAR virus, which any antivirus or antimalware scanner will detect. With a more malicious payload, these same techniques could easily result in a malware-infected endpoint.

HTTP Evader should not be confused with the well-known Evader tool originally released by Stonesoft. Since it seems to have disappeared from the Internet, [I made a copy of it available](https://drive.google.com/open?id=0B__UyP21zv4NUTYyNHREMGdJSTQ). Both tools operates on similar principles, though the focus of the Stonesoft/McAfee tool is far broader than HTTP traffic. Perhaps the reason one tool was confused for the other stems from the fact that **both** tools were used to demonstrate bypasses in Palo Alto Networks gear (as well as others).

The Stonesoft tool uses techniques noted by the SANS Institute in a whitepaper called [Beating the IPS](https://www.sans.org/reading-room/whitepapers/intrusion/beating-ips-34137). At the time this video was produced, Palo Alto Networks was vulnerable to these issues. As of Version 549 of their Application and Threat Content, **a full three years** after the SANS Institute paper was published, these issues are finally fixed.

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/cp-7Tl9gl5g" frameborder="0"></iframe></center>

The HTTP Evader tool is shown below. The video was posted in December 2015 and, to my knowledge, Palo Alto Networks gear is **still vulnerable** to the issues demonstrated:

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/Mo4LUh-5hYo" frameborder="0"></iframe></center>

If you're a Check Point customer? You're covered. Refer to the following SK articles for more details:

* [Check Point Response to Stonesoft IPS Evasion Techniques published on June 14, 2011](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk63621)
* [Check Point Response to HTTP Evader (http://noxxi.de/research)](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk109113)

Keep in mind that both Evader tools merely demonstrate *known* techniques to evade detection by modern security tools. Surely new evasion techniques will be developed, which will hopefully cause security vendors to react and update their products accordingly. I think it's safe to say Check Point will be at least one step ahead of Palo Alto Networks in keeping up with new developments in this area.

**Disclaimer**: My employer [Check Point Software Technologies](https://www.checkpoint.com) may or may not have differing views on this topic. These thoughts are my own.

**Edited to add** a link to the Stonesoft Evader tool on 5 March 2016.