---
layout: post
title: "VirusTotal: Not a Replacement for Real Threat Prevention"
date: 2016-05-06 21:00:00 -07:00
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
  feature: snake-oil.jpg
  credit: Hometown by Handlebar
  creditlink: http://hometownbyhandlebar.com/?p=11550
---
From [VirusTotal: Maintaining a healthy community](http://blog.virustotal.com/2016/05/maintaining-healthy-community.html):

> VirusTotal was born 12 years ago as a collaborative service to promote the exchange of information and strengthen security on the internet. The initial idea was very basic: anyone could send a suspicious file and in return receive a report with multiple antivirus scanner results. In exchange, antivirus companies received new malware samples to improve protections for their users. The gears worked thanks to the collaboration of antivirus companies and the support of an amazing community. This is an ecosystem where everyone contributes, everyone benefits, and we work together to improve internet security. 

VirusTotal is a great resource for users and security folks alike. It provides a quick way to validate how a number of antivirus engines view a particular file or URL (i.e. do they believe it is malicious or not). Think of it as a "peer review" for potential malware or even a "second opinion" when compared to whatever antimalware solutions you are using. Vendors who participate receive samples of files that aren't detected as malicious for the purposes of improving their products. 

VirusTotal is not meant to be used to compare different antimalware solutions. This is because the engines integrated into VirusTotal are not exactly the same version you might use on a desktop or on a network perimeter, which might take different information into account to determine whether or not something is malicious or might be configured differently than the "defaults" a particular vendor provides for a given engine. Also, signatures and engines change regularly, so even if a particular engine doesn't detect something when you checked, it may detect it later.

Something VirusTotal is most definitely not is a replacement for a proper antimalware solution. This is noted on the [VirusTotal about page](https://www.virustotal.com/en/about/):

> VirusTotal is not a substitute for any antivirus/security software installed in a PC, since it only scans individual files/URLs on demand. It does not offer permanent protection for users' systems either. At VirusTotal we think of our service as a second opinion regarding the maliciousness of your files/URLs.

It appears some vendors were using results from VirusTotal to supplement their products detection rates and not contributing their AV engine to VirusTotal. [The comments in this article](http://blog.eckelberry.com/a-bomb-just-dropped-in-endpoint-security-and-im-not-sure-anyone-noticed/) suggest the vendors that were doing this. [VirusTotal has now expressly forbidden this behavior](http://blog.virustotal.com/2016/05/maintaining-healthy-community.html):

> For this ecosystem to work, everyone who benefits from the community also needs to give back to the community, so we are introducing a few new policies to make sure that our community continues to work for years into the future. First, a revised default policy to prevent possible cases of abuse and increase the health of our ecosystem: all scanning companies will now be required to integrate their detection scanner in the public VT interface, in order to be eligible to receive antivirus results as part of their VirusTotal API services. Additionally, new scanners joining the community will need to prove a certification and/or independent reviews from security testers according to best practices of Anti-Malware Testing Standards Organization ([AMTSO](http://www.amtso.org/)). 

It's yet another case of [marketing hype not making you more secure](http://phoneboy.org/2015/12/06/marketing-hype-and-security-technology-that-actually-works/). Companies who have deployed products from these vendors are most assuredly less safe than they were before, though I suppose they could switch to [a number of VirusTotal alternatives](http://alternativeto.net/software/virustotal/) easily enough.

**Disclaimer**: I am not aware of any relationship between VirusTotal and my employer [Check Point Software Technologies](https://www.checkpoint.com). I'm also not aware of any relationship between my personal views that I've written here and Check Point's views on this matter, either. 