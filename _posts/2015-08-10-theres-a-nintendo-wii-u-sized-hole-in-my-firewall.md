---
layout: post
title: There's a Nintendo Wii-U Sized Hole In My Firewall
date: 2015-08-10 22:43:07 -08:00
type: post
published: true
status: publish
permalink: /2015/08/10/theres-a-nintendo-wii-u-sized-hole-in-my-firewall/
categories: []
tags: []
author:
  login: phoneboy
  email: dwelch@phoneboy.com
  display_name: Dameon Welch
---
In order to allow your Nintendo Wii-U to participate in multiplayer online games, you have to configure your router/firewall/whatever in [one of three ways per Nintendo](http://en-americas-support.nintendo.com/app/answers/detail/a_id/13214/p/431):

* Enable Universal Plug-n-Play (uPNP) on your router, which is [widely known to be insecure](https://community.rapid7.com/community/infosec/blog/2013/01/29/security-flaws-in-universal-plug-and-play-unplug-dont-play).
* Assign your Wii-U a static IP and use DMZ mode, which is opening your firewall to everyone on the Internet.
* Assign your Wii-U a static IP and forward all UDP ports (1-65535) to your Wii-U. Note that mapping a couple of ports isn't unusual, but when you're mapping this many ports, is basically the same thing as DMZ mode, thus not any better. 

None of these options are acceptable from a security point of view. Granted, I am reasonably security savvy and can mitigate the unnecessary risks involved with such a configuration. However, most consumers cannot and will not understand the risk they are undertaking.

[While I'm not exactly fond of a CyberUL](http://blog.erratasec.com/2015/06/cyberul-is-dumb-idea.html), if there was such a thing, this kind of configuration would clearly be non-compliant.

Of course, neither [Microsoft](http://support.xbox.com/en-US/xbox-360/networking/nat-error-solution) or [Sony](https://support.us.playstation.com/app/answers/detail/a_id/241/kw/nat) are much better, as they push the DMZ and uPNP as primary solutions first, but at least they offer solutions that don't require forwarding **all** ports like Nintendo does.

It's the kind of thing I'm surprised I haven't heard other security professionals rant about, honestly. It's certainly going to make me think twice about buying **any** product from Nintendo in the future.

**Edited to add on 10 Aug 2015**: Links to why uPNP is bad as well as explanations on why the other options Nintendo offers aren't much better.
