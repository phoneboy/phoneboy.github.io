---
layout: post
title: All The Security Tools In The World Won't Help If You Don't Do This
date: 2015-08-06 11:38:15 -08:00
type: post
published: true
status: publish
permalink: /2015/08/06/all-the-security-tools-in-the-world-wont-help-if-you-dont-do-this/
categories: []
tags: []
author:
  login: phoneboy
  email: dwelch@phoneboy.com
  display_name: Dameon Welch
image:
  feature: security-gate-bypass.jpg
#  credit: Steve Jurvetson
#  creditlink: https://www.flickr.com/photos/jurvetson/
---
In my travels as a Security Architect for [Check Point Software Technologies](https://www.checkpoint.com), I have seen many different customer environments. Granted, there is only so much I can see over the course of a couple of days, but I've seen enough to get a sense for where companies are generally at.

Based on the amount of security incidents in the news lately, as well as the number of engagements Check Point's Incident Response team is taking on, I'd say that companies generally have a long ways to go in securing all the things. And I've got a good sense for why.

No, it's not because customers don't have Check Point's latest security technologies, which third party NSS Labs continues to evaluate as "Recommended" as you can [Check Point's results in the 2015 NSS Labs Breach Detection Systems test](http://www.checkpoint.com/resources/nss-bds/index.html). You can have all the security products in the world and unlimited budget to buy them. They won't do you a bit of good if you don't do this one thing.

What is this thing? It's something you can implement with the security products and staff you already have today. It's hard work, no doubt, depending on the point you're starting from, but it will pay dividends down the road, regardless of the evolving threat landscape.

I'm talking, of course, about segmentation. What do I mean by that? In response to [Episode 126 of the Defensive Security Podcast](https://www.defensivesecurity.org/defensive-security-podcast-episode-126/), I crafted this tweet, which I think encapsulates the idea:

> [Segmentation is really about ensuring least privilege at all OSI layers](https://twitter.com/PhoneBoy/status/629132893609025536).

By least privilege, I mean the minimum privilege or access required to do a particular task and no more. By OSI layers, of course, I am referring to the [OSI model](https://en.wikipedia.org/wiki/OSI_model) that we all know and love.

To see how to apply this, let's evaluate two hosts, A and B and the "privileges" that A needs to initiate a communication to B. You could potentially do this with security zones as well, but if you're doing this exercise properly, you also need to do it for items within the same security zone as well.

Let's assume A should never talk to B under any circumstances. The best way to prevent this from happening is to make sure there is no physical or wireless path through which that can happen, i.e. Layer 1 of the OSI model. And by that, I mean no direct or indirect connection, either using a physical medium like Ethernet, or a wireless medium like Bluetooth or 802.11. That isn't to say a really determined bad guy can't somehow bridge the gap another way, but this automatically makes getting data between A and B much more difficult. 

Let's assume there is some *potential* connectivity between A and B. In almost all environments, that's a certainty. The next layer up is the Data Link Layer, Layer 2. If Host A and B are on different network segments, this layer may not apply so much. However, it can apply for hosts on the same subnet, particular on the wireless side. If there is no reason two hosts on a given subnet should ever need to talk to each other, and there is a way to prevent it at the switch or wireless access point, do it. 

Moving up the stack to Layers 3 and 4, otherwise known as IP address and port. What functions does a user on Host A need to access on Host B? What TCP/UDP ports are required for that communication? Do you really need all ports when, say, TCP port 443 will do? Those needs should be enumerated and explicitly permitted with access from all other hosts/ports denied.

Unlike in layers 1 and 2 where the ability to enforce a policy is pretty limited, there are a few places this policy can be enforced:

* A host-based firewall on Host A
* A host-based firewall on Host B
* A firewall located in the network path between Host A and Host B

This sort of policy can be implemented with nearly any firewall that's been deployed in the last two decades. It can (and should) be enforced in multiple places as well.

In current generation firewalls, these sorts of access policies can be augmented by incorporating identities associated with given IPs, e.g. from Active Directory, RADIUS, IF-MAP, or other sources. As the user logs into these identity sources for other reasons, an IP/user/group mapping is created on the firewall. The firewall can use this information to provide further granularity on the permitted traffic. For example, if someone from marketing sitting on the user segment wants to access a finance server, they will be denied, whereas someone from finance on that same segment will have no issue. This can happen regardless of the specific IP and doesn't even require any application-specific intelligence since identities are acquired out-of-band.

Once we get to Layer 7, things get a lot more complicated. What applications are we allowing Host A to use to Host B? How can I differentiate access between access to http://intranet.example.com versus http://phonebook.example.com when these websites are hosted on the same server at the same IP? Or what happens when I don't know where Host B actually is, because it's in the cloud? This is where current so-called "next generation" firewalls can help as they can easily allow access to things based on more than just an IP address. 

One thing to be aware of with application-aware firewalls is that some traffic needs to be allowed in order to identify the application being used. If the packets allowed in happen to be malicious, that could be problematic. This means you still need a strict IP/port based policy in addition to one that is application specific. Even Palo Alto Networks, whose marketing has historically said IPs and ports don't matter, [begrudgingly admits this point when pressed](http://researchcenter.paloaltonetworks.com/2012/12/app-id-cache-pollution-response/):

> We still recommend that you use the following security policy best-practices:
>
>   * For applications that you are enabling, you should assign a specific port (default or custom).
>   * For applications that you explicitly want to block, expand the policy to any port, to maximize the identification footprint. 
 
Network-based application-aware firewalls are one way to control application usage. Another is to implement Application Whitelisting on end user machines. By limiting what applications get run, you reduce the risk that something your users find on the Internet suddenly decides to make friends with all your machines. This is exceptionally difficult to manage, which is why it is something that is not seen in most environments.

For the applications that are allowed, there are controls on the server side as well, hopefully. Does the application have granular controls in place to limit the scope of what authenticated users are authorized to do? Are you actually using those? Are those critical applications being patched by their manufacturer for critical security bugs? Are those patches being deployed in a timely manner?

Active Directory is also an important thing to discuss. It has a pretty extensive permissions model. Are you actually using it? In other words, are your users--and administrators--configured with only the bare minimum permissions they need to perform their authorized functions? Are users using named accounts or generic accounts like "guest" or "administrator"? 

There is one other type of segmentation control to be considered, and that's around data that exists outside applications, such as Microsoft Office documents. Data can be protected with encryption, using technologies like full disk encryption, media encryption (USB sticks, etc), and document security (think DRM). You can prevent or track the movement of data in your enterprise (encrypted or otherwise) using a "port protection" product that restricts your ability to use USB drives, or an in-line network-based data loss prevention tool. 

I could go on and on. These controls are not particularly groundbreaking. Most of them have been around for years, yet in company after company, I observe one or more of these controls not being used to their full potential. Why they don't comes down to three basic reasons:

* Lack of knowledge about the controls
* A desire for convenience over security (includes not wanting to manage said controls)
* No budget

Going from a flat network to a segmented one is by no means easy. It will require a lot of planning and work in order to implement successfully. The good news is you can get started on the basics using the products you have today, i.e. without spending money. Over time, you can work your way up the OSI model, adding more sophisticated controls, like those new-fangled Breach Detection System that NSS Labs recently reviewed.

Even as the threat landscape and security tools evolve, a properly segmented environment built around least privilege principles will always be a good and necessary first line of defense.

**Disclaimer**: These are my own thoughts. If you're interested in what Check Point has to say on the matter, see the [Software-Defined Protection](http://www.checkpoint.com/products-solutions/software-defined-protection-sdp/index.html) framework.
