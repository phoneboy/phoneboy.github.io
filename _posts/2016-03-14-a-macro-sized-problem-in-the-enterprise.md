---
layout: post
title: "Macro-Sized Problems In The Enterprise"
date: 2016-03-14 21:55:00 -08:00
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
  feature: wordpwn2.jpg
  #credit: HTTP Evader
  #creditlink: http://noxxi.de/research/http-evader.html
---
I remember when Macro viruses in Microsoft Word were a thing more than a decade ago. They're definitely back with a vengence, and carrying far more dangerous payload than the Macro viruses of old. A couple recent examples are the [Locky Ransomware](http://blog.checkpoint.com/2016/03/02/locky-ransomware/) and [PowerSniff](http://researchcenter.paloaltonetworks.com/2016/03/powersniff-malware-used-in-macro-based-attacks/).

Microsoft disables Macros by default when you open documents in current versions of Microsoft Office. That said, it makes it very easy to enable them. Sometimes, malware-infested documents include text like this in them:

<center><img src="/images/wordpwn.jpg"></center>
<center><img src="/images/wordpwn2.jpg"></center>

Despite these very sketchy looking documents, **people actually disable macros** and before you know it, their system is infected with malware and you have a potential problem on your hands.

Is this really how it plays out? It depends on what other controls you have in your environment.

Check Point and Palo Alto Networks both claim to provide protections for these kinds of threats. However, not all protection is equal. From [PowerSniff Malware Used in Macro-based Attacks](http://researchcenter.paloaltonetworks.com/2016/03/powersniff-malware-used-in-macro-based-attacks/):

> Palo Alto Networks WildFire customers are protected against this threat, as all encountered files have been correctly flagged as malicious. Additionally, all C2 domains currently encountered have also been marked malicious. AutoFocus users can identify this malware using the PowerSniff tag.

Is it really protection? From [Palo Alto's documentation on WildFire](https://www.paloaltonetworks.com/documentation/70/wildfire/wf_admin/wildfire-overview/wildfire-concepts.html) with emphasis added by me:

> The key benefits of the Palo Alto Networks WildFire feature are that it can **discover** zero-day malware in web traffic (HTTP/HTTPS), email protocols (SMTP, IMAP, and POP), and FTP traffic and can quickly generate signatures to protect against future infections from the malware it discovers. **WildFire will automatically generate a signature** based on the malware payload of the sample and tests it for accuracy and safety. Because malware evolves rapidly, the signatures that WildFire generates will address multiple variants of the malware. As WildFire detects new malware, it **generates new signatures within 15-30 minutes**. 

Considering how easy it is to take a malicious file and change it so the file hash is not known, this is not a serious hurdle. More importantly, it means the proverbial Patient Zero who opens the file and enables macros is infected.

Check Point takes this a step further. In addition to blocking a file that is known to be bad by a signature/file hash and emualting the file to see if it's bad, the file is actually **held** while it is emulated. If the file is determined to be malicious, the file is not delivered to the end user, and appropriate indicators are delivered to ThreatCloud so others can benefit. 

While the file is being emulated, Check Point can also provide a reconstructed file to the end user that contains no macros. This is what Check Point calls Threat Extraction. In fact, I experienced this today when I received an email from a customer containing a Word Document. The email contained the following warning:

    ________________________________________
	This email's attachments were cleaned of potential threats by Check Point Gateway.
    Agenda Draft2.pdf : files(s) were successfully converted to PDF 
    Click here if the original attachments are required (justification needed). 
    ________________________________________

Instead of being delivered the original Word document, I was delivered a PDF that had the basic content of the file rendered in a harmless form. No option to enable macros at all. 

What if it turns out the file was genuine and I actually need the original? There's a link so I can download it, after confirming I trust the source. If the file actually **was** infected and Check Point's Threat Emulation detected that, I would not be able to download it. 

Sure, Threat Emulation could consider the file clean and it turns out not to be, but the chance of that is pretty low. Even so, you've added additional hurdles to prevent Patient Zero from getting infected in the first place. And, in case it happens, it's now a lot easier to track down who Patient Zero is. 

Microsoft Office documents aren't going anywhere, and neither are macro viruses. Make sure whatever solutions you deploy to protect against these threats have the ability to immediately block threats inline, **even if there is no signature for the threat**. Controls should be deployable inline and on managed endpoints for maximum protection.

**Disclaimer**: As noted above, my employer [Check Point Software Technologies](https://www.checkpoint.com) has a dog in this hunt with their [SandBlast Zero-Day Protection](http://www.checkpoint.com/products-solutions/zero-day-protection/index.html) offering. These thoughts, however, are my own. 