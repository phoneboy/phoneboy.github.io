---
layout: post
title: "CloudFlares with a Chance of Goatse"
date: 2017-02-10 12:00:00 -08:00
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
  display_name: Dameon Welch-Abernathy
#redirect_from:
#  - /2016/06/05/good-password-hygiene-key-to-protecting-social-media-accounts/
image:
  feature: this-is-fine.jpg
  #credit: speedygroundhog
  #creditlink: https://www.flickr.com/photos/speedygroundhog/
---
As I'm sure you've heard by now, [CloudFlare](https://www.cloudflare.com) had a case of [CloudBleed](https://blog.cloudflare.com/incident-report-on-memory-leak-caused-by-cloudflare-parser-bug/), causing what amounts to a massive privacy violation for *any* site that happened to use them. with one of threee specific features enabled: Email Obfuscation, Server-side Excludes, and Automatic HTTPS Rewrites. A [potential list of compromised sites](https://github.com/pirate/sites-using-cloudflare/blob/master/README.md) showed up, which may not be entirely accurate because plenty of sites use CloudFlare but may not necessarily use these features.

The advice that is given as a result of this bug?

> Check your password managers and change all your passwords, especially those on these affected sites. Rotate API keys & secrets, and confirm you have 2-FA set up for important accounts. This might sound like fear-mongering, but the scope of this leak is truly massive, and due to the fact that all Cloudflare proxy customers were vulnerable to having data leaked, it's better to be safe than sorry.
>
> Theoretically sites not in this list can also be affected (because an affected site could have made an API request to a non-affected one), you should probably change all your important passwords.

Which is fine if, like me, you actually use a password manager ([I recommend LastPass](https://lastpass.com)). However, it's not entirely complete advice as "HTTP cookies, authentication tokens, HTTP POST bodies, and other sensitive data" were leaked. Changing passwords won't suddenly fix this disclosure issue.

If the sites in question do a poor job invalidaing cookies and tokens, the fact you changed your password **won't solve the problem**. Think that's far fetched? [Think again](http://bgr.com/2017/02/16/yahoo-says-hackers-breached-your-account-in-new-attack-without-stealing-your-password/). Changing passwords also doesn't fix applications that may have communicated on the backend to a CloudFlare-backed site (either on your behalf or otherwise). The potential scope of this issue is...scary.

That said, I can't imagine every one who ever used service X over the last several months had their information disclosed. While this event increases the risk above zero, it's not clear by how much for a given user. Also, the impact of disclosure of a login cookie/token for my bank or a service like CloudFlare is *far different* than for a site like Techdirt, which [out of an abundance of caution is forcing everyone to reset their password on the site](https://www.techdirt.com/articles/20170224/16145636783/just-to-be-safe-were-resetting-all-techdirt-passwords-response-to-cloudbleed.shtml). 

I feel sorry for the average Internet user, who has seen umpteen of these notifications lately (just from Yahoo alone)! The advice of "change all your passwords" is quite simply untenable for the vast majority of Internet users. Even though I use a password manager as part of [good password hygeine](http://phoneboy.org/2016/06/09/good-password-hygiene-key-to-protecting-social-media-accounts/), I certainly don't have time to visit all the sites in LastPass, much less change all my passwords manually!

And, as I noted earlier, changing your password won't fully address the issue. Still, it's probably as a good a time as any to make sure your critical accounts are as protected as they can be. For me, that meant chaning my CloudFlare password and API key as well as enabling multi-factor authentication. I've also changed the password for a few sites listed on the [potential list of compromised sites](https://github.com/pirate/sites-using-cloudflare/blob/master/README.md). I will keep checking LastPass in case they decide to integrate this list of sites into their Security Challenge, which they've done in the past. 

Even if you do none of this, *my guess* is that the vast majority of the users won't be impacted by CloudBleed. At least I hope they won't be.

**Disclaimer**: My employer, [Check Point Software Technologies](https://www.checkpoint.com), didn't offer an opinion on this issue. The above thoughts are my own.