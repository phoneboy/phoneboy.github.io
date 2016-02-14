---
layout: post
title: Why SSL Decryption Is Important
date: 2015-08-24 14:21:03 -08:00
type: post
published: true
status: publish
permalink: /2015/08/24/why-ssl-decryption-is-important/
categories: []
tags: []
author:
  login: phoneboy
  email: dwelch@phoneboy.com
  display_name: Dameon Welch-Abernathy
---
From [Exclusive: The OPM breach details you haven't seen](http://fcw.com/articles/2015/08/21/opm-breach-timeline.aspx):

> According to the timeline, OPM officials did not know they had a problem until April 15, 2015, when the agency discovered "anomalous SSL traffic with [a] decryption tool" implemented in December 2014. OPM then notified DHS' U.S. Computer Emergency Readiness Team, and a forensic investigation began.

  The discovery of a threat to the background investigation data led to the finding two days later, on April 17, of a risk to the personnel records. US-CERT made the discovery by loading data on the April 15 incident to Einstein, the department's intrusion-detection system. On April 23, US-CERT spotted signs of the Dec. 15 exfiltration in "historical netflow data," and OPM decided that a major incident had occurred that required notifying Congress.

SSL/TLS traffic is pretty common. However, to most security tools, this traffic is opaque. Unlike SSH, which is [impossible to inspect securely](/2015/07/29/lies-damn-lies-and-inspecting-ssh-traffic-securely/), SSL/TLS can be inspected inline safely in a way that, for the most part, maintains the end-to-end security of the communications.

For this SSL/TLS traffic to be inspected, inline security gateways must examine the data as clear text. Encrypted data sent by a client to a web server is:

1. Intercepted by the security gateway and decrypted, effectively terminating the SSL/TLS connection by the client.
2. Inspected by the relevant security functions.
3. Encrypted again and sent to the designated web server, initiating a new SSL/TLS connection in the process,

When the security gateway terminates the connection, a certificate must be presented to the client. If the web server in question is protected by the security gateway, it can be configured with the private key of the website in question so it basically "pretends" to be the site. For a random site on the Internet, that's obviously not feasible, so the gateway generates a certificate *on the fly* and signs it with a preconfigured certificate authority the client PCs have been configured to trust. This ensures at least the client to firewall connection hasn't been compromised.

Once the connection is terminated on the security gateway, the traffic can be inspected or filtered just like regular plaintext traffic. The options available will depend on the vendor you have for your security gateway. On current (R77.x) versions of Check Point, you have the following security features at your disposal (assuming you are licensed for them): Data Loss Prevention (DLP), Anti Virus, Anti-Bot, Application Control, URL Filtering, Threat Emulation and Intrusion Prevention.

The firewall then initiates a connection as if it were the client to the server in question. The firewall validates the remote server presents a valid certificate for the site in question. If the server uses a self-signed certificate or some sort of certificate authority the firewall isn't familiar with, you will have to add it to the configuration as valid. This step ensures the remote end of the connection is valid and trusted--something that [SSH inspection is unable to do](/2015/07/29/lies-damn-lies-and-inspecting-ssh-traffic-securely/). 

There are a couple of issues with SSL decryption:

1. There may be privacy and legal regulations on the use of this feature depending on the country in which you are located. Please review your local laws and regulations.
2. If client certificates are needed for authentication, SSL decryption cannot be used. This makes sense since the firewall won't have these cerificates.
3. Applications or site that use certificate pinning will fail since the certificate authority for these sites will differ once SSL decryption is enabled.
4. When you visit a site with an extended validation (EV) certificate and SSL decryption is happening, you will not see an EV cert. This is because it is not possible to generate an EV cert with a typical certificate authority key.
5. You cannot do SSL decryption on a network the general public uses. This is because you need to be able to distribute a certificate authority key to your end users. One cannot get a publicly-trusted root CA key for this purpose as certificate authorities do not allow this practice. Certificate authorities used for this purpose get revoked pretty quickly, [as happened to a government agency in Turkey](http://arstechnica.com/security/2013/01/turkish-government-agency-spoofed-google-certificate-accidentally/).
6. Decrypting SSL/TLS traffic will have a performance impact. That said, it's generally not an "all or nothing" thing. You can choose to be selective as to which traffic gets decrypted and which does not. 

Bottom line: understading what hides inside your SSL/TLS traffic is critical to finding and eliminating network-based threats. A number of security gateway vendors, including Check Point, offer this feature, and it should be leveraged where possible. More information about Check Point's implementation of this feature can be found in [sk65123](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk65123) in SecureKnowledge.
