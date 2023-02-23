---
layout: post
title: "Apple vs. The FBI Demonstrates Convenience Versus Security"
date: 2016-02-24 22:00:00 -08:00
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
  feature: ios-pin.jpg
  #credit: cloud2013
  #creditlink: https://www.flickr.com/photos/dennisredfield/
---
While there are definitely bigger issues at play in the case of Apple vs. The FBI, issues that have been discussed ad-infinitum, there's actually something a bit more innocuous to look at, and [it was discussed](http://naplay.it/801/1-14-24) on my favorite podcast, [No Agenda](http://noagendashow.com), hosted by Adam Curry and John C. Dvorak.

Recall that [the actual court order](https://assets.documentcloud.org/documents/2714001/SB-Shooter-Order-Compelling-Apple-Asst-iPhone.pdf) is asking for Apple to make it possible *on a specific device* to allow the PIN code to be brute-forced in an automated fashion without introducing unnecessarily delays and without wiping the device after 10 missed guesses. This is because the PIN code unlocks the encryption key for the device, which would allow the FBI to access the device. 

To explain how this works, I'll quote from [Apple's iOS Security Guide for iOS 9](https://assets.documentcloud.org/documents/2714001/SB-Shooter-Order-Compelling-Apple-Asst-iPhone.pdf):

> The passcode is entangled with the device’s UID, so brute-force attempts must be performed on the device under attack. A large iteration count is used to make each attempt slower. The iteration count is calibrated so that one attempt takes approximately 80 milliseconds. This means it would take more than 5½ years to try all combinations of a six-character alphanumeric passcode with lowercase letters and numbers.
>
> The stronger the user passcode is, the stronger the encryption key becomes. Touch ID can be used to enhance this equation by enabling the user to establish a much stronger passcode than would otherwise be practical. This increases the effective amount of entropy protecting the encryption keys used for Data Protection, without adversely affecting the user experience of unlocking an iOS device multiple times throughout the day.
>
> To further discourage brute-force passcode attacks, there are escalating time delays after the entry of an invalid passcode at the Lock screen. If Settings > Touch ID & Passcode > Erase Data is turned on, the device will automatically wipe after 10 consecutive incorrect attempts to enter the passcode. This setting is also available as an administrative policy through mobile device management (MDM) and Exchange ActiveSync, and can be set to a lower threshold.

It's tricky to provide very high security for devices while at the same time maintain usability. This is a classic case of balancing convenience and security and Apple should be lauded for their efforts here. *With all of these limitations Apple puts in place*, including the end user enabling the "Erase Data after 10 failed passcode attempts" option, even a 4-digit PIN *can* provide a reasonable balance between usability and security.

That said, I generally agree with [Adam Curry's assessment](https://www.facebook.com/gldnspud/posts/10154322473817289?comment_id=10154322495977289) in that a 4-digit PIN code isn't really that secure. This is because end users generally pick PIN codes that are easy to guess if you know even a little bit about the person in question. Given [the passwords people choose](http://gizmodo.com/the-25-most-popular-passwords-of-2015-were-all-such-id-1753591514), this should be no surprise.

Even with a 4-digit PIN and the "Erase Data after 10 failed passcode attempts" option turned off, the ever-escalating passcode lockout provides some level of protection. Same with limiting passcode entry to the touch screen. Without those limitations in place, it would be trivial to brute code a 4-digit PIN code (about 15 minutes) or even a 6-digit PIN code (about a day). 

Which is, of course, why the FBI wants the ability to remove those protections. And why, if you care even a little bit about the security of the data on your mobile device, that you should use a longer, more complex passcode on your device. Given that even without those restrictions, it takes roughly 80 milliseconds to check each PIN/passcode attempt, it doesn't have to even be that long or that complex to keep the passcode from being guessed in your lifetime. 

**Disclaimer**: My employer [Check Point Software Technologies](https://www.checkpoint.com) might have differing views on this topic. These thoughts are my own.
