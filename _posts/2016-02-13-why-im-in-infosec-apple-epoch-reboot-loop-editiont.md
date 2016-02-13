---
layout: post
title: "Why I'm in Information Security, Apple Epoch Reboot Loop Edition"
date: 2016-02-13 13:50:00 -08:00
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
  feature: broken_ipad.jpg
  #credit: phoneboy
  #creditlink: https://www.flickr.com/photos/armydre2008/
---
Undoubtedly you've heard by now of the bug that occurs when you manually set the date back on your 64-bit iOS device to 1/1/1970: the device gets locked in a reboot loop. If not, there's an article on [Ars Technica](http://arstechnica.com/apple/2016/02/64-bit-iphones-and-ipads-get-stuck-in-a-loop-when-set-to-january-1-1970/) or [this read on Reddit](https://www.reddit.com/r/apple/comments/458cqz/changing_time_date_settings_to_jan_1_1970_will/) that explains the issue.

Would a reasonable person actually set the date on their phone back to Jan 1st 1970? In most situations, no, but they can be socially engineered to do so, which I will admit I was with [someone sharing an image like this one](http://imgur.com/gallery/EpPy85r). The good thing is I had the sense to do it on my *secondary* iOS device and had backups. I also know how to disassemble my phone to unplug the battery, which is the only reliable way I've seen to recover from the problem.

Ok, social engineering issues aside, this problem requires physical access to the device, right? Not so fast. iPhones checks in with an NTP server to get the current system time. NTP is a UDP protocol, as such [can easily be spoofed]. A person who knows how NTP works might say that NTP won't allow such large timejumps. Has anyone tested Apple's implementation to ensure it doesn't allow this? I don't know, but it's certainly a potential exploit vector.

There should be no setting on any device that causes it to become a paperweight like this. Whether a reasonable user would change that setting or not is really irrelevant because a malicious actor can exploit facts like this to cause mischief.

When it comes to bugs like this, it's never about whether a reasonable user could trigger it--they can be socially engineered into doing so--it's about how a malicious actor can leverage the bug to cause unauthorized disclosure, alteration, or distruction of information or assets. The fact I can reason my way through this *and enjoy doing so* is why I'm still in Information Security today.

**Disclaimer**: I have no idea what my employer [Check Point Software Technologies](https://www.checkpoint.com) thinks about any of this. These thoughts are my own. 