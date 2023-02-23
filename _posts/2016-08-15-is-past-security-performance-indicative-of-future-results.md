---
layout: post
title: "Is Past (Security) Performance Indicative of Future Results?"
date: 2016-08-15 11:00:00 -07:00
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
  display_name: Dameon Welch
#redirect_from:
#  - /2016/06/05/good-password-hygiene-key-to-protecting-social-media-accounts/
image:
  feature: dino.jpg
  #credit: speedygroundhog
  #creditlink: https://www.flickr.com/photos/speedygroundhog/
---
It's a phrase you will see in the fine print of any document related to past performance of a money manager, mutual fund, or managed financial account: "Past performance is not necessarily indicative of future results." The same disclaimer could easily be applied to information security products and their ability to stop threats. 

The most obvious technology this statement applies to: anti-virus. While it does a great job at doing what it was designed to do--block known, malicious files--it has limitations in the kinds of malicious files it can identify. It also can be a source of additional vulnerabilities, [such as what recently was discovered in Symantec's Endpoint products by Google](http://www.scmagazine.com/vulnerabilities-in-symantec-products-create-worst-case-scenario-users-urged-to-update/article/506853/). I suspect any widely security technology will suffer a similar fate: either the technology itself is attacked or the technology is rendered ineffective through innovation by the bad guys.

Where I think "past performance" is indicative with security products is: how quickly are security issues discovered with the product remediated. Because let's face it: every security product will be vulnerable to some discovered issue at some point. What ultimately matters is: how quickly do you remediate these issues. 

For a company that uses "Prevention is Non-Negotiable" as their marketing message, [Palo Alto Networks](http://paloaltonetworks.security) is not so good at fixing security issues discovered in their products. Here's the latest example from the [PAN-OS 7.1.4 release notes](https://www.paloaltonetworks.com/documentation/71/pan-os/pan-os-release-notes/pan-os-7-1-4-addressed-issues#91886):

![PAN OS 7.1.4 Fixed CVE](/images/panos-714-cve.png)

The [National Vulnerability Database](https://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2015-7547) lists this as a high-severity issue. The time to issue a public patch? **Nearly 6 months from date of discovery**. Based on the response times Check Point has seen when [security vulnerabilities were responsibly disclosed to them](https://www.checkpoint.com/3rd-party-security-vulnerabilities-advisories/), this timeframe doesn't seem all that surprising.

To be fair, it's possible that Palo Alto Networks did a risk assessment on these issues and determined the likelihood of exploit is low enough that they didn't need to fix these issues urgently. They may be right, but when you preach "Prevention is Non-Negotiable," taking 6 months to fix a known security vulnerability in your product *just looks bad*. Actions, ultimately, speak louder than marketing.

**Disclaimer**: My employer, [Check Point](https://www.checkpoint.com), believes in addressing issues like this quickly. These views, however, are my own. 