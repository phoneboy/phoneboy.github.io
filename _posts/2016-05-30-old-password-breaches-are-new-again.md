---
layout: post
title: "Old Password Breaches are New Again"
date: 2016-05-30 12:00:00 -07:00
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
image:
  feature: wall-breach.jpg
  credit: Gabriel
  creditlink: https://www.flickr.com/photos/cod_gabriel/
---
In the past couple of weeks, a couple of old breaches of social media sites have come into the news again, mostly because the data from the breaches of MySpace, LinkedIn, Tumblr, and some site called Fling that I never heard of before, [are for sale on the dark web](https://www.troyhunt.com/the-emergence-of-historical-mega-breaches/). Aside from chatter on Twitter, the first thing that could be deemed a "formal" notification came from Troy Hunt's site [Have I Been Pwned](https://haveibeenpwned.com/), something I recommend everyone subscribe to as he seems to do a better job of notifying people than the providers do.

You might wonder why we who care about information security care about years-old breaches from social media sites. It's pretty simple: most "normal" people use the same login and password everywhere they go on the web. It's also quite possible they didn't get the memo the first time these breaches occurred, either.

And let's be honest, even if you changed your password when the breach was first announced, what are the odds you changed the password since then? Most likely, you haven't and now is as good a time as any to change your password for these sites, if for no other reason than to leverage improved password hashing algorithms these sites are surely implementing.

Of course, a couple of other pieces of advice to implement:

* **Different Passwords on Every Site**: As noted above, password re-use is what makes these older breaches relevant to a lot of people. You can mitigate this risk in the future by using unique passwords on each site you authenticate to.
* **Use Two Factor Authentication**: Even if someone is able to crack your password, two factor authentication should slow down any determined hacker. That said, two factor authentication is still not something the majority of people do because it's still not easy. Also, systems have a reliance on SMS (which itself can be compromised) or a token that operates only on a *single* smartphone. What happens when you lose your phone?
* **Use a Password Manager**: The primary benefit of a password manager is the ability to use unique, complex passwords on all the sites without having to type or remember them. Yes, your password manager becomes a huge target, but the security benefits outweigh the risks. 

[LastPass](https://lastpass.com) is my password manager of choice. Works across all the platforms I use (Mac, PC, Linux, Android, and iOS). At $12/year, it's an absolute no-brainer. Yes, I know a lot of people like 1Password, but I find their apps a much more expensive propopsition.

Perhaps one of my favorite features of LassPass is their Security Challenge. It evaluates all the passwords I have in my vault to see which passwords may have been compromised, ones that are weak, ones I've reused, and ones that haven't been changed in more than a year. This allows me to quickly identify which accounts might need a new password--one I can make significantly more complex thanks to LastPass. Note that even without using the Security Challenge, I'm warned when I reuse a password--a very good thing. 

**Disclaimer**: My employer Check Point Software Technologies might have a different point of view on passwords, these are my own.