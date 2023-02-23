---
layout: post
title: "​Good Password Hygiene Key To Protecting Social Media Accounts"
date: 2016-06-09 15:00:00 -07:00
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
redirect_from:
  - /2016/06/05/good-password-hygiene-key-to-protecting-social-media-accounts/
image:
  feature: passwords.png
  #credit: Gabriel
  #creditlink: https://www.flickr.com/photos/cod_gabriel/
---
​From [Miscreants breach NFL’s Twitter account, reveal its weak password](http://arstechnica.com/security/2016/06/nfls-breached-twitter-account-falsely-claims-commissioner-goodell-is-dead/)

> Online miscreants took over the National Football League's Twitter account and used it to falsely report the death of league commissioner Roger Goodell.
>
> During the brief span that @NFL was taken over, it followed exactly one new Twitter account—specifically, @IDissEverything, which has now been suspended. Before the account was suspended, it claimed the password protecting the NFL Twitter feed was "olsen3culvercam88." The Daily Dot said someone connected to the IDissEverything account claimed the password was revealed after someone managed to get into the email of a social media staffer at the NFL, where we found the credentials in a message." It's still not clear how the group got access to the e-mail account.

Between all the various password dumps that have taken place recently—[32 million Twitter credentials, anyone?](http://techcrunch.com/2016/06/08/twitter-hack/), generally poor password choices, and even poorer password hygiene, it seems a lot of social media accounts are getting hacked these days. Including [those of Facebook CEO Mark Zuckerberg](http://www.bizjournals.com/sanfrancisco/blog/techflash/2016/06/linkedin-breach-mark-zuckerberg-hacking-security.html) and [Twitter co-founder Ev Williams](http://mashable.com/2016/06/08/ev-williams-twitter-hacked/).

Given how people are slow to change their habits, I don't see this trend changing anytime soon. To make matters worse, social media services themselves can have security issues, too. [My colleagues at Check Point helped Facebook find a pretty serious issue in their Messenger application](http://blog.checkpoint.com/2016/06/07/facebook-maliciouschat/).

Earlier this week, I was interviewed by reporter [Annie Gaus](https://twitter.com/AnnieGaus) for an article on these credential breaches. [The advice I was quoted giving in the article](http://www.bizjournals.com/sanfrancisco/blog/techflash/2016/06/ceos-hacked-zuckerberg-facebook-twitter-linkedin.html) shouldn't be anything you haven't heard before. Now might be a good time to implement it, especially if you happen to be a high-profile person or someone who manages the social media accounts of organizations. 

## Use Strong, Unique Passwords For Each Site

If there's one thing these recent site hacks taught us, it's that using the same password on every site is a bad idea. People still generally pick passwords that, in the [immortal words of Spaceballs](http://www.imdb.com/title/tt0094012/quotes), an idiot would have on their luggage!

So, yes, use a unique password on each site. Also, make sure it's not something simple. Complexity is good. Length is better. Long and complex is even better!

My favorite way to get a sense how good of a password I've chosen is to use the [Password Haystack page](https://www.grc.com/haystack.htm) from Gibson Research. It's not a "password strength meter" but it gives you a good idea how long it would take for your password to be guessed via brute force. There's also some good advice on this page on how to construct a password that is both easy to remember and strong enough to hold up to brute force guessing.

## Use A Password Manager

While it is true a password manager creates a single point of attack—and failure—a good password manager has several benefits that outweigh the risks. This assumes you use it with a strong master password, of course.

* Provides a way to securely sync password vaults across multiple computers and mobile devices.
* Allows you to use more complex passwords without having to remember them.
* Provides an indication of the last time you used a specific password.
* Provides an indication of the last time you changed a specific password.
* Provides a mechanism to tell you when you are using the same password on multiple sites.

[LastPass](https://lastpass.com) is my password manager of choice. Other people like [1Password](https://1password.com/). I can't speak for others that may exist, though I can assure you they are not all created equal.

## Use Two Factor Authentication

Many services now offer Two Factor Authentication, either using SMS or the relatively standard TOTP/HOTP tokens implemented by Google Authenticator, Authy, and others. While it does prevent someone from brute-force guessing your password, it doesn't prevent someone from phishing you. Be careful out there!

## If You're Not Using a Social Media Account, Close It

Given people's propensity to use the same login and password everywhere, and the ever increasing odds of sites getting hack, close social media accounts you're not using. That said, you might consider changing the password to something complex before you close it on the off chance the service doesn't actually delete your data and the site later gets hacked.

## Assume All Social Media Is Public, Act Accordingly

This is not necessarily a security issue, and wasn't one of the items highlighted in the article I was quoted in, but it is a privacy issue and important none the less.

Personally, I don't think Facebook and the like are intentionally trying to make everything you do public (though plenty have good reason to think that). I'm saying this because, like everything else, social media accounts can and will be hacked. Or are vulnerable to issues through their API. Also, people can easily screenshot any social media interaction—including and especially private ones—and make it public instantly.

You're better off assuming anything you input into social media, SMS, iMessage, WhatsApp, Telegram, or whatever can and will be made public. Act and share accordingly.

## If You Have To Share Social Media Passwords, Do It Securely

While it is generally bad practice to share any passwords, individuals in companies who maintain a corporate social media presence often end up having to share credentials as a practical matter. Twitter is one common example.

If you absolutely have to do this, then you should not share passwords over email, SMS, WhatsApp, and so on in plaintext. These mechanisms, or the device you run them on, could be compromised in some way.

An encrypted container of some kind is the way to go. For example, I use Microsoft Word documents protected with [Check Point Capsule Docs](https://www.checkpoint.com/products/capsule-docs/), which encrypts the document and allows me to restict documents to specific individuals only. Only those individuals will be able to read the document. I can also restrict what they are able to do with the documents as well.

Another way to accomplish the same task: LastPass, which also has a password sharing feature.

## Change Your Passwords Occasionally

Even if you use complex, unique passwords on every site, changing passwords occasionally is not a bad idea. Once a year is probably often enough, though some events may necessitate changing your password more often:

* If it's a shared password (see above), change it if someone no longer needs access to the account (e.g. when they leave the organization or change roles).
* A breach is reported on a specific site. 
* If you got a password reset email that you didn't request. 

Changing your password will allow your password to be hashed with stronger algorithms, which sites will often switch to over time. 

**Disclaimer**: If you don't know by now, I work for Check Point Software Technologies. However, these are my own thoughts.
