---
layout: post
title: "Why Check Point Security Management Is Still The Gold Standard"
date: 2016-04-03 10:00:00 -08:00
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
image:
  feature: fw1r80.jpg
  #credit: HTTP Evader
  #creditlink: http://noxxi.de/research/http-evader.html
---
In a recent customer meeting, one of my colleagues was telling a customer how the central management capabilities of Check Point Security Gateways is lightyears ahead of what any other vendor provides for their products and has been for as long as I've been supporting Check Point products--20 years now! This is not just my opinion, but that of third party analyst firms as well as customers. 

The question one might ask: how come after all these years, no one has been able to seriously challenge Check Point's management capabilities? Sure, other vendors offer centralized management, but no one can operate at the same scale. A single Check Point Multi-Domain Management installation can potentially manage hundreds and thousands of gateways, where competitors struggle managing tens or hundreds of gateways. 

To me, the answer is very simple: it's in Check Point's DNA and it goes back to the very first versions of the product. 

The first version of FireWall-1 I used was 2.0. At that point, it was managed using an OpenLook GUI on SunOS or Solaris. In version 2.1, a Windows-based client was added, which eventually became the way to manage the firewall policy. This GUI has seen numerous enhancements over the years, but I'm sure even people who haven't been using Check Point as long as I have could use those oldest GUIs.

The concept of separating the management from the firewall? It was in version 2.0, though I'm told it was in a 1.0 release (not the first one, but a subsequent one). Large scale management at service provider scale, a.k.a. Provider-1, was added in 1999, first as a separate management product, then integrated into the maintrain product in the R71 release.

As more features became integrated into the product, Policy Editor became SmartDashboard and the number of GUIs proliferated, each focusing on its own part of monitoring or managing Check Point products. Even SmartDashboard had a number of tabs for managing the different Software Blades. 

Certain competitors to Check Point still like to highlight the various tabs in SmartDashboard as a weakness of the product. You have to allow something in the firewall, then in IPS, App Control, etc, instead of just having a single, unified policy. While it's a fair criticism, you can't just make a drastic change to how things are done when you have more than 100,000 customers. The methods chosen in the R7x releases were pragmatic and allowed customers to leverage the functionality in Software Blades without having to hand-tweak hundreds or even thousands of rules built around access control only. 

Prior to R80, perhaps one of the bigger management changes was the addition of SmartLog. I remember when I was asked to perform usability testing on this product before it was released. I was presented with a relatively spartan interface that reminded me of the Google homepage. I was able to quickly and easily find stuff that would have been possible in SmartView Tracker, of course, but would have taken far longer, particularly if I had to search across many log files (SmartLog indexes and searches across all your log files).

And now, after many many months in development, [the R80 release of management is finally available](http://supportcontent.checkpoint.com/solutions?id=sk108623)! It's now a single management UI (SmartConsole) which incorporates both policy and logging. Security policies are now unified across the blades (though for full functionality, this requires gateways running R80.10 and above). Even while managing older gateways, there are numerous usability ehnancements that make it quicker and easier to manage your security infrastructure.

Automation, something that was not a strong point in earlier Check Point releases, is now a first class citizen. A robust CLI and Rest API is available complete with support for concurrent administration (in read/write mode, even!) and granular permissions to control who can do what. There is also a web-based interface to access logs, events, and reports. 

While R80 was formally released on 31 March 2016, numerous customers have been using R80 for weeks and months through the Early Availability program. I decided to wait until the formal release to migrate my management to R80, which involves a fresh installation and the use of the standard migration tools to export/import the previous configuration. Rasther than leverage that process, I decided to hand-configure everything from scratch. 

Actually, that's not entirely true. I used the CLI in order to create the vast majority of the network objects I needed for my relatively simple policies. The R80 CLI is far easier than using dbedit to perform the same tasks. If I was feeling exceptionally clever, I could have also done it using the rest-based API, which allows for all kinds of integrations with other third party tools. 

There are a few things missing in R80 Management that I'm sure will be added over time. Some of the really cool features in R80 today like nested policy layers or a fully unified policy will require R80 gateways (which are not available yet). 

One thing which will take some time to get used to is the lack of a built-in "Demo Mode." I remember when you would invoke it by logging into the server *local (later given an official tickbox on the login screen), which would bring up a locally hosted database so you could see the GUI in action. This approach had some limitations, namely certain features that required a live management server would not work. As R80 Management is definitely more than just UI, a virtual machine with a populated configuration will be provided for this purpose in the near future. 

If you haven't kicked the tires on R80 Management yet, there's no excuse now that it has been generally released. It shows the level of commitment Check Point continues to make to keep ever-increasing complexity easier to manage than ever.
