---
layout: post
title: "The Security Industry: Lead By Example"
date: 2016-01-29 09:22:00 -08:00
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
  feature: lead_by_example.png
  credit: Ken Whytock
  creditlink: https://www.flickr.com/photos/7815007@N07/
---
If the security industry itself can't be bothered to fix security issues in a timely manner, how can we expect customers to apply the patches in a timely manner? Shouldn't we be leading by example?

Generally speaking, [Check Point](https://www.checkpoint.com) (where I work) is pretty quick to respond to reported issues. In some cases, fixes have been out **in hours**. Some of Check Point's competitors? Not so quick. Here are a couple recent examples.

## FireEye's Year Old Vulnerability

A couple people from Check Point reported an issue to FireEye on 24 July 2014. While the issue was reported on one of their products (their 'EX' product), the issue actually affected several of their products. A "fixed" version of code for the product we reported on was issued on 7 July 2015, **349 days** after it was first reported. This is how the issue was reported in their [Q4 2015 Security Vulnerability advisory](https://www.fireeye.com/content/dam/fireeye-www/support/pdfs/2015-q4-security-vulnerability-advisory.pdf):

![FireEye Vulnerability](/images/fireeye-vuln.jpg)

To be fair, the issue *was* fixed in some products in a much shorter time, but for one product, it was about **15 months**. 

The acknowledgement by FireEye is misleading. First of all, the employer of the reporters was **not mentioned** as it was for others in the advisory (it's Check Point, as noted previously). Second of all, the actual issues reported are **more serious** than the somewhat misleading description FireEye chose to provide. Even with the description provided, I disagree with the "low" severity rating. Social engineering attacks, anyone?

## Palo Alto Networks Evading For Three Years

I've largely covered [the vulnerability in question](/2015/12/24/palo-alto-networks-evading-the-truth/) on a previous post. The one update I can provide is that 3 years after the [original SANS Institude paper being published highlighting the deficiencies](https://www.sans.org/reading-room/whitepapers/intrusion/beating-ips-34137), Palo Alto Networks finally issued an update to their Application and Threat Content that addresses the issues. Or at least they addressed the issues demonstrated by the [666 different ways to bypass Palo Alto Networks](https://www.youtube.com/watch?v=cp-7Tl9gl5g) video, which are based on the same principles.

## More Examples

Check Point has actually found and responsibly disclosed a number of vulnerabilities in a number of common services and software products, including those of competitors. [A presentation has been posted on SlideShare](http://www.slideshare.net/MotiSagey/check-point-vulnerability-research-53146368) providing the details. 

## Conclusion

Every product out there is going to have security vulnerabilities found in it, including and especially products designed to keep your environments secure. What separates the mature, market-leading vendors from the others is **how** you respond to such reports. 


