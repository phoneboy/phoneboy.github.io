---
layout: post
title: The Security Impediment
date: 2015-12-27 23:12:00 -08:00
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
  feature: s_demmer_pile_of_sand.jpg
  credit: S Demmer
  creditlink: https://www.flickr.com/photos/kre8ivps/8055350928/in/photolist-dgPMbQ-bLLJxz-dYfAAn-6vdvDZ-sP3ShN-2SvFuT-pWWoft-biJ4di-ydyZ8N-dEEFLs-ce8xvh-NrVuA-3gUaU7-6oJyud-7haBqm-eet9xK-9xp3VC-nq6qL4-dB1cAm-BgWAaW-BNyGyS-akoCFp-6gYYKM-5SdmHr-7iNi5L-4GcGcq-95ER8q-cnrUqC-4h68fr-6p5vko-d4Dgoy-CJPdj-cJViH-7Gb57j-5kTHrq-7NNvd9-5RFZWr-6Z3LPi-8gCnDh-8ts8zT-5dE7KJ-p4XoV-aQA19T-6cMA6r-7drrPv-81qofF-6yrnAv-6Hj18C-eLH9rm-5zKmJk
---
From [Chip Cards Take So Long, Some Retailers Disabled Them For The Holidays](http://www.forbes.com/sites/kateashford/2015/12/27/chip-cards-take-too-long/):

> It could be that, among other things, retailers are reacting to shoppers’ sentiments. One in five consumers names transaction time as their biggest concern when using an EMV-enabled credit or debit card, according to [a recent survey](http://www.harbortouch.com/blog/one-in-five-consumers-say-paying-with-chip-enabled-credit-cards-takes-too-long/) by point-of-sale firm Harbortouch.
>
> It takes about seven to 10 seconds to process a chip card at the register versus two to three seconds to process a swipe. “While seemingly small, during busy times like the holidays, these increased processing times could add up quickly,” Jared Isaacman, founder and CEO of HarborTouch, said in the press release.

This is not a hypothetical problem that's pointed out here. In a super-busy
store, slowing down the entire point-of-sale system for added security can
mean less customers go through the checkout, meaning the retailers make
less money.

The problem is even more acute in stock trading. Delays of even a fraction of
a second in receiving a trade order can cost serious money.

Organizations of all kinds often make a tradeoff between transaction speed
and ensuring that transaction is authorized and legitimate. They usually
err on the side of speed versus secure.

There is no right or wrong answer, because part of security is *accepting
risk* for specific behavior that is less secure. This can happen because:

* The cost to mitigate the risk is too high
* The cost of failure of a mitigating security control is exceptionally high
* The likelihood of occurence of the relevant events are very low

Security measures are often viewed--rightfully so, in some cases--as impeding
business. Of course, they also enable business as well. I doubt e-Commerce
would have flourished the way it did had Netscape not invented Secure
Sockets Layer.

Those of us in the security industry need to ensure the solutions we are 
offering are not impeding business while providing a high level of
security and reliability. That way, organizations won't have to accept
as much risk as they do today.
