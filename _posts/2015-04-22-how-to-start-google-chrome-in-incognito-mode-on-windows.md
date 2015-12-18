---
layout: post
title: How To Start Google Chrome In Incognito Mode On Windows
date: 2015-04-22 20:35:00 -08:00
type: post
published: true
status: publish
permalink: /2015/04/22/how-to-start-google-chrome-in-incognito-mode-on-windows
categories: []
tags: []
author:
  login: phoneboy
  email: dwelch@phoneboy.com
  display_name: Dameon Welch-Abernathy
---
I know a few articles have been written about this topic already elsewhere. That said, I sometimes will do a blog post so if I need to find something again, I know it will exist on my own blog.

For a while I had been using [WhiteHat Aviator](https://www.whitehatsec.com/aviator/), which is a fork of Google Chrome that has many privacy options enabled by default. Since, at the time of this writing, it is currently *five major versions* behind mainline Chrome, it's gone Open Source, and there doesn't appear to be any recent checkins on the GitHub project, and there will [likely be some difficulty updating the existing browser](https://plus.google.com/+JustinSchuh/posts/69qw9wZVH8z), I'm guessing we probably won't see an update unless someone undertakes a major effort.

With that in mind, I'm looking to try and configure Google Chrome as securely as possible. There is the [Google Chrome Privacy Whitepaper](https://www.google.com/chrome/browser/privacy/whitepaper.html) and another independently maintained page on [Privacy and Security Settings in Chrome](https://noncombatant.org/2014/03/11/privacy-and-security-settings-in-chrome/). You could also use something like the [Disconnect Search plugin](https://chrome.google.com/webstore/detail/disconnect-search/hmobfennjmjnkdbklhcnnfbhfibedgkk). However, none of these pages solve one feature I really enjoyed about Aviator: starting up the browser in Incognito Mode. This does two important things:

* Doesn't log website browsing history at all

* Clears all cookies on browser exit

However, Google Chrome does not offer an easy way to do this, but it can be done in two specific places: The shortcut you use to start Google Chrome on your Windows machine and the Windows registry. 

First, the shortcut. Find it on your computer, right-click on it and select Properties from the pulldown menu. Add a --incognito to the end of the Target field (note, it's a space, two dashes, then incognito) and click Apply.

<center>
<img src="/images/19d5309b1ff516e7d0c38afdea54dd43.png">
</center>

This will cause Chrome to start in Incognito Mode when launched from the shortcut. However, this will not cause web links you click on in other apps to also launch into the Incognito Mode. To do that, you need to edit the registry as follows:

* Open Regedit (From the Start Menu, type regedit)

* Find the following registry key: HKEY_CLASSES_ROOT\ChromeHTML\shell\open\command

* Edit the registry string (double click on "(Default)"), adding a --incognito to the value data between the quote and the double hyphen and click Ok.

<center>
<img src="/images/ee385063224adb48b5cb4ccd35281f4b.png">
</center>

Congratulations, you're now permanently incognito in Chrome. Note if you want to use some of your extensions in Chrome, you will need to manually enable them for Incognito Mode by clicking on the hamburger menu in the upper right corner of the browser window (the three vertical lines), selecting Settings, and then clicking on Extensions. Check the "Allow in Incognito" checkbox for each one.

While it's all fine and good that I can configure this stuff by default, I really wish Google had a one-click option that just enabled all this stuff by default.

To do something similar on the Mac, try the [Google Chrome Incognito app.](https://github.com/willfarrell/Browsers/tree/master/Google%20Chrome%20Incognito.app) For Linux, it will likely be a distribution specific answer, but [this should work for recent versions of Ubuntu](http://askubuntu.com/questions/159630/how-do-i-make-google-chrome-open-incognito-by-default).
