---
layout: post
title: "Why Can't I Choose What to SSL Inspect Based on Application?"
date: 2016-02-15 00:50:00 -08:00
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
  display_name: Dameon Welch-Abernathy
image:
  feature: ssl_inspect_policy.png
  #credit: phoneboy
  #creditlink: https://www.flickr.com/photos/armydre2008/
---
SSL Decryption is a feature that is in current versions of the Check Point Security Gateway. It's in other competing products as well. I wrote a description of the technolofy in a previous blog post entitled [Why SSL Decryption Is Important](/2015/08/24/why-ssl-decryption-is-important/).

All implementations of this feature have a configurable policy so you can decide what traffic to decrypt. Here is an example policy from a Check Point Security Gateway, which can use IP addresses or URL Filtering Categories:

<center>
<img src="/images/ssl_inspect_policy.png" alt="SSL Inspection Policy">
</center>

Some people would prefer to use applications (e.g. YouTube), but I just don't see a way to do that without reducing the overall security posture. Maybe someone more clever than me can explain the flaws in my logic.

The way Check Point determines whether or not a given IP requires SSL inspection is to actually *man in the middle* the first connection to a given IP (assuming the policy is configured appropiately and just the "site category" needs to be determined). In the first few packets of that MITM connection, we can determine conclusively what URL the end user is going to (or the app is using), put an IP and category entry in the local cache, and inspect the traffic on that connection. Even if a URL isn't used, the certificate information is in the first few TCP data packets, which gives us something to put a URL category to. If further connections to that IP should be SSL Inspected, the firewall will do so per the policy.

Sometimes the "man in the middle" process can break specific applications (e.g. because they are using Certificate Pinning). Or a URL isn't being used. Or, worse, the SSL site in question requires *Client Authentication* which will completely break when you attempt to man in the middle an SSL connection. This is why in the latest (R77.30) release, there's now a mechansim called Probe Bypass that can be enabled as described in [sk104717](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk104717). 

Some applications cannot be identified using just the certificate. Google is a great example of this as they use wildcard certificates across a number of their properties. Even Server Name Indiciation, which exists to remediate this issue, doesn't work consistently across all browsers and servers. Thus we're left with the original certificate as-is.

Let's assume we're ok with not man-in-the-middling traffic until we're certain it's an app we want to perform SSL Inspection on. When you're identifying applications beyond using IPs and ports, you actually have to let some traffic pass through the firewall. 

(Is a traditional IP/port related policy still relevant? Absolutely, despite what some [Check Point competitors](http://www.paloaltonetworks.com) like to say in their marketing, which even *they will admit* [if pressed on the issue](http://researchcenter.paloaltonetworks.com/2012/12/app-id-cache-pollution-response/).)

If we don’t man in the middle the first connection to an IP, and thus allow the application to be identified first before deciding to SSL Inspection, we run the risk of allowing encrypted traffic for an application we actually want to inspect. Malicious applications could easily exploit this behavior, pretending to be an unidentifiable application, thus connections would never be SSL Inspected. 

---

**Disclaimer**: This is my own thinking. My employer [Check Point Software Technologies](https://www.checkpoint.com) may have a different stance on this matter.

**Edited to add** reference to Probe Bypass on 15 Feb 2016 (some hours after I originally published)