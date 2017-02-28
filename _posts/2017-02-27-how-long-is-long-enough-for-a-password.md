---
layout: post
title: "How Long is Long Enough for a Password?"
date: 2017-02-27 17:00:00 -08:00
# modified: 2014-12-24
type: post
published: true
status: published
# permalink: 
categories: []
tags: []
author:
  login: phoneboy
  email: dwelch@phoneboy.com
  display_name: Dameon Welch-Abernathy
#redirect_from:
#  - /2016/06/05/good-password-hygiene-key-to-protecting-social-media-accounts/
image:
   feature: lulzsec-62k-password-tag-cloud.png
#  credit: kc green
#  creditlink: http://gunshowcomic.com/648
---
As much as we might want to see different authentication methods available, passwords aren't going anyway anytime soon. This means a significant part of our security online comes down to choosing good passwords. 

There are three basic rules for choosing good passwords:

1. The more complex the better
2. The longer the better
3. Don't use the same password on multiple sites

Some services like Office 365 are [being criticized for only allowing 16 character passwords](https://answers.microsoft.com/en-us/windows/forum/windows_10-security/please-increase-the-16-character-password-limit/5de69b9a-ac5c-4891-94c5-349dc25957ae). Some services offer even less than this. 

If you actually do a little math, and choose the characters in your password carefully enough, perhaps using a tool like [LastPass](https://lastpass.com) to generate and manage the passwords, even a 16 character password is more than strong enough to withstand a brute force attack!

To demonstrate that, I'm going to use the [GRC Haystacks](https://www.grc.com/haystack.htm) tool just to show the search space required in order to find a given password. Yes, I know there are some in the security community that poo-poo some of the contributions to information security that Steve Gibson has made. The tool is merely expressing the results of math and is being used for illustrative purposes. 

A password can theoretically have four different types of characters:

* Uppercase characters (26 possible options)
* Lowercase characters (26 possible options)
* Numbers (10 possible options)
* Special characters (33 characters)

This gives us a total of 95 possible values for a given character of a password. Note that this may vary from site to site as some sites might restrict the special character space. Some sites might even allow for emoji, which I am excluding since outside of smartphone platforms, these are not universally available.

Let's assume we pick a 16 character password that leverages all four character types and is relatively random. The time required to exhaustively search this space with a tool like [hashcat](https://hashcat.net/hashcat/) or [John The Ripper](http://www.openwall.com/john/)? A much longer time than I can even conceive of!

![16 Character Complex Password](/images/password-16-char-complex.png)

What about if I choose a 16 character password that is all lowercase, but random? Even if a lot of computing power is thrown at the password hash, we're still looking at several years of computing time:

![16 Character Lowercase Password](/images/password-16-letter-lowercase.png)

However, by adding a little bit of complexity, say, uppercase characters, the search space suddenly increases by orders of magnitude!

![16 Character Upper and Lowercase Password](/images/password-16-character-upperlower.png)

Even a 12 character complex password has a pretty large search space to search through:

![12 Character Complex Password](/images/password-12-char-complex.png)

All of this assumes you are choosing truly random characters for your password. If you're using a well-known password manager, it's probably random enough. Obviously, if you choose dictionary words for your password, or simple variations thereof, the odds of someone guessing your 16 character password are *much* higher.

Then again, how might someone perform a brute force attack on your password? Certainly [if someone leaks the hashed passwords](https://haveibeenpwned.com/) it's possible. It's likely not the result of an online brute force attack as that is likely to be detected and/or blocked and will most certainly take much longer.

And yes, the amount of time it takes to validate a password is a factor here. To illustrate this, let's talk passcodes on phones. At least on Apple devices, if you enable the wipe feature, Apple will wipe the device after 10 failed passcode attempts. The phone only allows passcode entry via the screen and each attempt takes 80 milliseconds to process, [as I discussed previously](http://phoneboy.org/2016/02/24/apple-vs-the-fbi-demonstrates-convenience-vs-security/). After a few failed attempts, the phone will lock out additional attempts for a period of time. Which means, it's not like someone can pick up your phone and a few seconds later, your phone is wiped. 

With those constraints in place, how long and complex of a passcode do you really need to keep yours phone from being unlocked by someone other than you? Probably nowhere near as many as you think, so long as you avoid obvious and common ones. For the sake of argument, let's look at an 8 digit passcode:

![8 Digit PIN](/images/password-8-digits.png)

To exhaustively search this space, assuming 80ms per guess and no other limiting factors, it would take about 103 days to try all possible combinations. Since there are other limiting factors as noted above, including the fact that the ability to automate passcode guessing is limited, it would take a bit longer. Of course, if the iPhone owner enabled the "erase after 10 failed attempts" option, all bets are off. 

The bottom is line is, when you actually look at the math, you don't need quite as long of a password as you think you do. Assuming the limit is at least 12 characters and *all* special characters are supported, you can make a complex enough password to sufficiently mitigate most brute force attacks. Even a 16 character password with just mixed case letters has a pretty large search space, assuming your passwords have sufficient entropy.

Having said all that, I'm all for sites supporting longer passwords. Length does allow people to make more complex passwords that are far easier to type, which can be good for people just learning [good password hygiene](http://phoneboy.org/2016/06/09/good-password-hygiene-key-to-protecting-social-media-accounts/). Also, if it helps people *feel* more secure to have a longer password and adding support for longer passwords is trivial, why not support it?

Obviously, if there is a massive increase in available computing power anytime soon, some of these assumptions will have to be reexamined. That said, I suspect we'll have bigger issues to deal with than just the security of our passwords. 

**Disclaimer**: My employer, [Check Point Software Technologies](https://www.checkpoint.com), didn't offer an opinion on this issue. The above thoughts are my own.