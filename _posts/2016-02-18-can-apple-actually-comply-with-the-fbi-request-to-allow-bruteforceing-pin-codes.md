---
layout: post
title: "Can Apple Actually Comply With The FBI Request To Allow Bruteforcing Pin Codes?"
date: 2016-02-18 22:30:00 -08:00
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
  feature: slide_to_unlock.jpg
  #credit: phoneboy
  #creditlink: https://www.flickr.com/photos/armydre2008/
---
For a moment, anyway, ignore the politics of whether or not Apple *should* comply with the FBI's request to assist them in unlocking a particular iPhone relevant to a highly publicized terrorism case, which [has been court ordered](https://assets.documentcloud.org/documents/2714001/SB-Shooter-Order-Compelling-Apple-Asst-iPhone.pdf). Let's talk about whether it's actually possible or not, based on the information available and what I know is possible.

To summarize, the request is to provide "reasonable technical assistance" to achieve the following three things:

1. Disable the auto-erase function (which can happen if this feature is enabled)
2. Allow submission of passcodes via something other than the touchscreen
3. Disable the ever-escalating delays that Apple introduces when you enter incorrect passcodes

This would allow the FBI to effectively brute-force the PIN code on the device, assuming the owner of said device used a simple 4-digit passcode (very likely). A 6-digit passcode, which is the new default in iOS 9.2, might take a little longer. If it's an actual strong password, the FBI might be waiting a long time to actually unlock the phone.

I don't think there is any debate that Apple can write firmware that accomplishes the above tasks. The trick, of course, is getting the changed firmware onto the device. The only way I know of that can happen on a device where the passcode is not known is by using the Device Firmware Upgrade (DFU) mode. 

Just for kicks, [I put one of my iPhones into DFU mode](https://www.theiphonewiki.com/wiki/DFU_Mode) and plugged it into one of my computers. I got the following warning:

<center><img src="/images/dfu_warning.png"></center>

Loading new firmware on the device will erase the device, which kind of defeats the purpose the FBI is trying to achieve. That is, of course, unless Apple has designed a way to prevent that from happening in certain cases. [Dan Guido seems to think this is the case](http://blog.trailofbits.com/2016/02/17/apple-can-comply-with-the-fbi-court-order/) and if you read [Apple's Legal Process Guidelines](https://www.apple.com/privacy/docs/legal-process-guidelines-us.pdf), it seems to suggest this is possible, at least in versions of iOS prior to 8.0:

> For iOS devices running iOS versions earlier than iOS 8.0, upon receipt of a valid search warrant issued upon a showing of probable cause, Apple can extract certain categories of active data from passcode locked iOS devices. Specifically, the user generated active files on an iOS device that are contained in Apple’s native apps and for which the data is not encrypted using the passcode (“user generated active files”), can be extracted and provided to law enforcement on external media. Apple can perform this data extraction process on iOS devices running iOS 4 through iOS 7. Please note the only categories of user generated active files that can be provided to law enforcement, pursuant to a valid search warrant, are: SMS, iMessage, MMS, photos, videos, contacts, audio recording, and call history. Apple cannot provide: email, calendar entries, or any third-party app data. 

It's possible Apple didn't need new firmware to obtain access to the data it outlines above, it could simply interrogate the device in DFU mode and the device would give the information up. Even if a new firmware load is required to accomplish this task, it's possible that as part of improving device security by encrypting all the data, Apple also closed the loophole that allowed them to put a new version of iOS on the device in DFU mode without erasing it. As the device in question is reportedly running iOS 9.0, *the entire argument* for whether this is technically possible or not hinges on the answer to this question. 

The only other method available to Apple: hacking the actual device in much the same way jailbreakers do. The very same thing [John Mcafee is offering to do for free](http://www.ibtimes.co.uk/john-mcafee-i-can-hack-san-bernardino-iphone-fbi-apple-backdoor-like-giving-our-enemies-1544651) using his army of hackers with 24-inch purple mohawks, 10-gauge ear piercings, and tattooed faces--people not likely to be under the employ of the FBI.

**Edit 19 February 2016**: I asked Dan Guido via a comment about whether or not you could load new firmware via DFU mode. He said it could be loaded as a ramdisk which would leave the user data alone. Whether this could actually accomplish what the FBI is asking for is still not known, but the fact you can do this certainly makes it seem a lot more plausible.

<center><img src="/images/dfu_ramdisk.png"></center>

Regardless of whether or not this is technically possible, Apple is right to challenge this court order. The implications go well beyond this one iPhone and will impact our digital rights globally for decades to come.

**Disclaimer**: I haven't asked what my employer [Check Point Software Technologies](https://www.checkpoint.com) thinks about all this. These thoughts are my own.
