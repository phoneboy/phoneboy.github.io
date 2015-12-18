---
layout: post
title: Lies, Damn Lies, and Inspecting SSH Traffic Securely
date: 2015-07-29 16:44:05 -08:00
type: post
published: true
status: publish
permalink: /2015/07/29/lies-damn-lies-and-inspecting-ssh-traffic-securely/
categories: []
tags: []
author:
  login: phoneboy
  email: dwelch@phoneboy.com
  display_name: Dameon Welch-Abernathy
---
SSH is a wonderful tool for accessing remote systems via a CLI. It is encrypted, if set up properly, I can verify I am talking to the correct server using mutual key exchange and I can tunnel all kinds of stuff over it. If you're so inclined, you can even use an SSH tunnel as a SOCKS proxy. 

And therein lies the problem. SSH represents a potential way to bypass security controls, in much the same way as HTTPS. To mitigate this threat, security gateways can man-in-the-middle HTTPS and SSH to "see" inside the traffic and make further security decisions on it. 

Fortinet has a feature called SSH Inspection that performs this man-in-the-middle on SSH. Palo Alto Networks calls their similar feature SSH Decryption. Throughout this post, I am going to refer to the general technology as SSH Inspection but my comments apply to both implementations. 

Conceptually, SSH and HTTPS are man-in-the-middled in similar fashions even though the underlying protocols are very different. While SSH Inspection provides more visibility and control, there are some tradeoffs you should be aware of. 

First, a brief explanation of what happens to web traffic when HTTPS is man-in-the-middled by a security gateway. For most web (looking) traffic, provided you can easily distribute a new Certificate Authority to client PCs, end users will be none the wiser their HTTPS is being inspected unless they check the "lock" on their browser to see what Certificate Authority signed the key of the remote server.

The security gateway ensures the connection between it and the destination site hasn't been tampered with by validating the server certificate the same way a regular web browser would. The security gateway can even be configured to disallow connections to sites where this validation cannot take place. This gives a high degree of confidence that even though the security gateway is inspecting the connection, you are ultimately speaking with the legitimate destination server.

There are problems with this approach. If a specific application/site utilizes Certificate Pinning, then the security gateway-generated SSL certificate will be rejected because it is signed by a different Certificate Authority. Likewise, when client certificates are used for authentication, the process will fail through a gateway performing SSL Inspection via man-in-the-middle techniques as there is no way for the security gateway to perform client authentication on behalf of the user.

The good news is that the number of applications and webssites affected by these limitations are few and far between. Specific exceptions for these applications and sites can be included in the relevant SSL Inspection policy and those applications will work as before.

When SSH traffic is similarly inspected man-in-the-middle style, the exact same issues come up with SSH for the exact same reasons with a far greater impact. This is because, unlike HTTPS where client authentication is rare, mutual authentication of client and server is the norm with SSH.

When SSH Inspection is in use, end users are limited to password-based authentication for SSH connections as it is not possible for the security gateway to send the end user's SSH key. Furthermore, you as an end user have no easy way to verify you are connecting to the correct host as the security gateway presents its *own* generated SSH host key instead of that of the remote server.

Why is that an issue? SSL/TLS utilizes certificate authorities, meaning some third party vouches for the veracity of a given certificate presented. In the case of man-in-the-middle for SSL, the firewall is, in essence, vouching for the veracity of the certificate as it is signing the certificate, and we trust the firewall, right?

SSH does not use certificate authorities, meaning that if the connection is being man-in-the-middled, we have no idea *who* is man-in-the-middling the connection, we just know the SSH host key changed. This might be ok if the firewall actually verifies the veracity of the SSH host key presented. 

**From what I can tell, neither Palo Alto Networks or Fortinet (two companies that have SSH Inspection features) provide a way to verify that a particular SSH host key hasn't changed.** As SSH does not make use of certificate authorities, there is no way to automatically verify that the key was changed *legitimately*. A human could do the verification if they could see the new host key coming from the remote SSH server. With SSH Inspection enabled, the user will never see that key, **which leads to a potentially interesting attack vector**:

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/ACxNbkTo1qQ" frameborder="0" allowfullscreen></iframe></center>

And in case you're thinking I'm just picking on Palo Alto Networks, **Fortinet's SSH decryption has the same flaw**:

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/JUHfbj9O4RQ" frameborder="0" allowfullscreen></iframe></center>

To summarize, when we man-in-the-middle SSH, we can only use password authentication and we lose the ability to verify we are connecting to the desired server. And what security benefits do we get from this degredation of SSH security? The ability to:

* Prevent Port Forwarding (including "X11 Forwarding)
* Block the use of ssh "commands" or "shells" 
* Possibly prevent file transfers provided they are done in a way the security gateway knows about (and there are many, many ways to do this over the CLI)
* Possibly log commands issued over SSH

Personally, I don't see the value of this SSH Inspection feature as it degregades SSH security unacceptably and provides little benefit above and beyond what you would get by **blocking SSH entirely** except for specific, trusted individuals accessing specific, known servers. If this is not feasible, I provide some suggestions for [inspecting SSH connections securely](http://securitytheater.phoneboy.com/2015/07/30/the-right-way-to-inspect-ssh-connections/) in another blog post.

**Disclaimer**: I'm not sure what [Check Point Software Technologies](https://www.checkpoint.com) thinks about this issue as I didn't ask. These thoughts are my own.

*Edited to add video embed on 13 Aug 2015*
