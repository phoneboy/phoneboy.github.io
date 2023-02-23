---
layout: post
title: The Right Way To Inspect SSH Connections
date: 2015-07-30 07:28:10 -08:00
type: post
published: true
status: publish
permalink: /2015/07/30/the-right-way-to-inspect-ssh-connections/
categories: []
tags: []
author:
  login: phoneboy
  email: dwelch@phoneboy.com
  display_name: Dameon Welch
---
When talking with Check Point customers, a common request I hear is for the ability to "decrypt" SSH traffic, see inside of said traffic, and make security decisions based on what it finds, including blocking tunneling. [In my last post](/2015/07/29/lies-damn-lies-and-inspecting-ssh-traffic-securely/), I explain how the SSH Inspection feature provided by a couple of Check Point's competitors actually works and why you might want to think twice about using it. If you don't believe my analysis, check out the following video, which shows how **these SSH decryption features can be used against you**:

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/ACxNbkTo1qQ" frameborder="0" allowfullscreen></iframe></center>

And in case you're thinking I'm just picking on Palo Alto Networks, **Fortinet's SSH decryption has the same flaw**:

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/JUHfbj9O4RQ" frameborder="0" allowfullscreen></iframe></center>

There is clearly a need to control what happens with SSH connections. When used by the general user population, SSH is similar to an anonymizer like Tor or UltraSurf which hide the true intent of the encrypted traffic and serve no business purpose. How should you handle this requirement without comrpromising the security of SSH the way SSH Inspection does?

**My general stance on allowing SSH still stands**: SSH should only be permitted for specific individuals to specific hosts with a clear business need for this kind of access. That said, let's assume you want to do more than just allow/block SSH access, prevent tunnelling, and log what your users do over SSH without compromizing the security of SSH in the process. 

Many years ago, when I worked for Nokia, whenever I was sitting in the office and wanted to SSH out to the Internet, I had to go through an explicit SSH proxy server that operated on the following principle:

1. You SSHed explicitly to the proxy
2. You were prompted by the proxy for the desired destination IP and username to use on the remote server
3. You logged into the remote SSH server

It was not possible to use port forwarding using this configuration. You also got some visual indication that the remote host key changed as the proxy would keep track of that the same way a regular SSH client would. This still didn't allow authentication with an RSA key, but it is still an improvement. 

Nokia's SSH proxy was something that was home grown. You could do something similar with a jump server that authorized individuals could use to ssh to other hosts with full ability to use RSA keys and verify a remote server's host key. You can prevent port forwarding and the like by disabling tunneling in the SSH daemon on the jump server. You could also set up whatever type of logging is necessary on this jump server to meet your requirements. The servers that could be connected to from this jump server would be allowed or blocked by your security gateway. Additional logging should be set up on the permitted servers as well. 

If setting up a jump server is too much work, you still want to allow users to SSH to random hosts, and you're just concerned that people might use SSH for things other than an interactive SSH session (e.g. tunneling), a way limit this is to implement QoS on all SSH connections. You would have to choose a limit that provides acceptable performance for interactive terminal sessions but makes tunneling other things very slow. On a Check Point Security Gateway, you can achieve this in the Application Control rulebase using the "limit" Action. 

At the end of the day, it's important to understand what your actual requirements are with respect to controlling and logging SSH traffic so the right controls can be put into place. The methods described herein balance security and usability far better than the SSH Inspection features some security gateways provide.

**Disclaimer**: While I did get some [link love from Check Point](http://blog.checkpoint.com/2015/08/12/ssh-decryption-opens-door-to-very-old-security-vectors/), whom I work for, the thoughts herein are my own.

*Edited to add video embeds and link to Check Point blog post on 13 Aug 2015*
