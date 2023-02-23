---
layout: post
title: "Marketing, Information Security, and The Jobs To Be Done"
date: 2016-01-24 17:00:00 -08:00
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
  feature: jobs-to-be-done.png
  credit: Innovators Toolkit
  creditlink: http://innovatorstoolkit.com/content/technique-1-jobs-be-done
---
A marketing message came across my LinkedIn feed, which is starting to look a lot like my Facebook feed. It was about *Anti-Virus* and how a particular vendor's product uses less memory than competing products. Nothing about efficacy. Of course, in a highly commoditized market, one would assume (rightly or wrongly) that the efficacy of all products in the space are similar.

Of course, even if you speak to efficacy, it's largely a statement about how the product did in a specific test and, like the oft-repeated financial services disclaimer "past performance is not indicative of future results." 

This kind of marketing misses the mark. It's marketing to technical people about things only technical people would care about. The people who make the decisions to purchase said products aren't always technical. Sadly, I see it all too often from all corners of the information security space.

## The Jobs To Be Done Framework

I was first introduced to this framework as a result of listening to [The Critical Path](http://5by5.tv/criticalpath), a podcast "contemplating the causality of success and failure in the evolving story of mobile computing and related industries." Host Horace Deidu actually uses this framework quite a bit in the analysis he does on the podcast. The framework comes from Harvard professor Clayton Christensen and was developed as a way to look at customer needs by focusing on their fundamental motivation. Or, [as the Innovators Toolkit says](http://innovatorstoolkit.com/content/technique-1-jobs-be-done), *highlight the human need you're trying to fulfill*. 

To summarize the framework very briefly, people buy goods and services are bought because they perform certain jobs. These jobs can be sorted into main jobs and secondary jobs (usually in conjunction with a main job). These jobs have both functional and emotional aspects to them. People take all of these things into account when deciding which product or service they will "hire" to do these jobs. [A more detailed explanation of the framework](http://innovatorstoolkit.com/content/technique-1-jobs-be-done) is available on the Innovators Tooklit site.

To bring this into context of the current discussion: companies don't buy information security products or even hire information security professionals "just because"--there's an underlying motivation to do so. A "job to be done," if you will. 

## What Are The Jobs To Be Done?

Every organization has its own reason for existing, a job for which it hired to perform for someone else. In turn, they hire individuals, products, and services to do specific jobs to support that main task.

Why are information security professionals hired? Generally because the organization feels they have *information assets* that require protecting. In many organizations, people who originally served a different purpose are now tasked with protecting information. This can be a bit like using a screwdriver to drive in a nail. Sure, you might be able to actually use it for that in some circumstances, but it's not the right tool for the job. Unlike a fixed object like a screwdrivers, people can actually evolve their skills and talents *becoming* the right tool for the job. 

What are the jobs to be done in information security? Quite a lot, actually, but they mostly boil down to protecting the confidentiality, integrity, and availability of information assets. This is known as the CIA Triad (not to be confused with the Central Intelligence Agency in the US Government). 

Confidentiality, integrity, and availability are meant to be taken in equal measure. When it's not possible to ensure all three equally, I often see organizations err on the side of availability over the other two elements, which often leads to the DAD Triad: disclosure, alteration, and destruction.

## Back To Marketing: Speaking To The Jobs To Be Done

In looking at some of Check Point's competitors in the space, I see words like detection, protection, or even "take decisive action." Are these the jobs you want done with respect to your information assets, or would you like something stronger?

Check Point uses much stronger language: prevention, as in Next Generation Threat Prevention. Or if you're talking about the SandBlast sandboxing product for zero-day malware, another term that is used: threat extraction (as in extracting the threats from documents). In other words, *Check Point's products prevent threats from reaching your information assets*. 

Palo Alto Networks, to their credit, also uses the word prevention, and it's definitely a better "job to be done." Perhaps that's why both Check Point and Palo Alto appear as "leaders" in the most recent Gartner's Magic Quadrant for Enterprise Network Firewalls.

## Actually Performing The Job To Be Done

One thing to note about Gartner is they measure perception. Reality is measured by another organization: NSS Labs. They do this through a series of group tests performed on various security products and provide the results to paying customers. Vendors such as Check Point can also purchase marketing rights to the reports as well. If you're interested, you can see [how Check Point performed in the latest Breach Detection Systems test](http://www.checkpoint.com/resources/nss-bds/index.html). The TL;DR version: a "recommended" rating was received, as Check Point has received on numerous group tests over the last several years.

One vendor is conspicuously absent in the latest BDS test: Palo Alto Networks. NSS Labs CTO Bob Walder had something to say about this:

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Question:If a vendor not only refused to participate in a test,but actively blocked our purchase of their product,would you want to know?</p>&mdash; Bob Walder (@bwalder) <a href="https://twitter.com/bwalder/status/567714065057730560">February 17, 2015</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

Given that [PAN's EULA forbids publishing third party test results](https://www.linkedin.com/pulse/what-palo-alto-networks-still-afraid-dameon-welch-abernathy), the only way to validate any of their claims is in your own lab. Should they make your shortlist, I highly recommend testing it *head-to-head* with other, competitive solutions ensuring you follow [PAN's Best Practices](https://www.paloaltonetworks.com/documentation/70/pan-os/pan-os/threat-prevention/best-practices-for-securing-your-network-from-layer-4-and-layer-7-evasions.html).