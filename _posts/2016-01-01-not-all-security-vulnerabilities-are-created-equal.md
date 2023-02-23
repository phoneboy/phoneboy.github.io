---
layout: post
title: Not All Security Vulnerabilities Are Created Equal
date: 2016-01-01 01:44:00 -08:00
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
#image:
#  feature: patch_all_the_things.jpg
#  credit: dargadgetz
#  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
---
<img style="float: right;" src="/images/i_dont_always_patch_all_the_things.jpg">

From [Press Backspace 28 times to own unlucky Grub-by Linux boxes](http://www.theregister.co.uk/2015/12/17/press_backspace_28_times_to_own_any_grubby_linux_box/):

> A pair of researchers from the University of Valencia's Cybersecurity research group have found that if you press backspace 28 times, it's possible to bypass authentication during boot-up on some Linux machines.
>
> The problem's not a kernel nor an operating system problem, but rather one in the very popular bootloader Grub2, which is used to boot an awful lot of flavours of Linux.
> 
> Essentially, if you enable Grub2's password protection during system startup, it won't do you much good – it can be easily defeated. (Luckily, the vast majority of distributions of Linux do not enable this by default.)

I don't want to say this is a non-issue, because it's not.
That said, it helps to have some perspective on the impact of a potential
vulnerability so you know what you should do about it at what priority.

When I worked in the TAC back when I was at Nokia, I was the guy who would
decipher the latest "OMG, my scanner found your firewalls are vulnerable to
this new CVE, fix it." This meant reading the actual CVE to figure out if
this could lead to remote code execution, cross-site scripting, or similar.

Because of how Nokia IPSO was hardened, many of the vulnerabilities had
no particular impact, either because the vulnerable component wasn't there
or it was configured in a more secure configuration than the default.

Or, better yet, in order to leverage the exploit, you had to have a
specific kind of access to the machine (say, shell access) that could
lead to far more dangerous things than the vulnerability in question.

This Grub bug is one of those things. First of all, this bug only shows up in
a non-default configuration and requires physical access to boot. Ok, so maybe
also a serial console might work, too. Either way, this limits the potential
scope of a potential attack. Furthermore, if you actually have physical
access, unless you've performed some sort of drive encryption, that physical
access could be leveraged to, say, steal or clone the drive. Which is a far
more serious threat.

In the grand scheme of things, this bug would not be a huge priority to deploy
a patch for in all cases. Unlike, say, the [backdoor in Juniper/Netscreen gear](https://www.techdirt.com/articles/20151219/07481133129/us-govt-agencies-freak-out-over-juniper-backdoor-perhaps-theyll-now-realize-why-backdoors-are-mistake.shtml)
which can be remotely exploited.