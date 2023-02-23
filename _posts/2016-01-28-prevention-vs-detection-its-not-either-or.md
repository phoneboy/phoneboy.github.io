---
layout: post
title: "Prevention vs. Detection: It's Not Either Or"
date: 2016-01-28 22:22:00 -08:00
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
  feature: there_are_no_threats.jpg
#  credit: Ben Watts
#  creditlink: https://www.flickr.com/photos/benwatts/
---
From [No, Virginia, It Does NOT Mean That!](http://blogs.gartner.com/anton-chuvakin/2016/01/25/no-virginia-it-does-not-mean-that/): 

> Here are my top 5 reasons why DETECTION excellence does NOT automatically mean you can have PREVENTION: [Uncertainty, Timing, Vague Signals, False Positives, and Detecting From Exploration]

This article, written by a VP of Research at Gartner, completely misses the most obvious element of a prevention stance: the ability to actually block the malicious traffic. That, of course, [requires segmentation](/2015/08/06/all-the-security-tools-in-the-world-wont-help-if-you-dont-do-this/) and some security control that can actually block the traffic in question.

(By the way: anyone who truly believes detection is better than prevention should turn off their firewalls right now. Go ahead, turn them off. Oh wait, you actually want to block some traffic you know you don't want? That's not what a "detect only" mindset allows for.)

I've seen several organizations use various "threat intelligence" (either internally gathered or a combination of internal and external intel) and simply using basic firewall functionality to block access to known malicious sites. This might be automated or it might not, meaning there is a gap between something "bad" being discovered and that configuration being implemented on your firewalls.

A much better approach would be to use tools that are able to understand in realtime what traffic is good or bad, consulting external threat intelligence that is updated automatically and continually to the enforcement points, and actually have the traffic blocked. Sure, you may get the occasional false positive, but is a false negative actually better?

Sure, no solution is going to stop 100% of all threats, because even preventative controls that consult the best threat intelligence in the world isn't going to know about everything. By definition, it can only block *known* bad traffic and, with an inline malware sandboxing solution, a good percentage of the zero-day malware can be blocked too. It's still not going to get everything. The silver lining is that a lot of the breaches that occur actually use *known* bad traffic. Thus, a comprehensive in-line threat prevention solution located at strageic points in the environment will be a net-positive for just about every organization.

For those things we can't block that are bad and truly unknown, we still need to detect those things, and just as importantly, respond in a timely manner.

**Disclaimer**: Check Point (where I work) has a great [next generation threat prevention](http://www.checkpoint.com/products-solutions/threat-prevention/) solution. That said, the above are my own thoughts.


