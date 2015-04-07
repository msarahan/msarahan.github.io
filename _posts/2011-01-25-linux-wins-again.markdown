---
layout: post
status: publish
published: true
title: Linux wins again!
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 146
wordpress_url: http://t3hmikez0r.com/?p=146
date: '2011-01-25 14:27:35 -0800'
date_gmt: '2011-01-25 22:27:35 -0800'
categories:
- Uncategorized
tags:
- Nerd
comments: []
---
<p>I've been cursing the wireless card in my computer since I pieced it together last week.  It's an Asus PCE-N13.  It didn't require any extra driver installation under either Windows 7 x64 or Ubuntu 10.10.  However, the signal was very poor in Windows, with constant drop-outs, and it would not detect any networks at all in Ubuntu.</p>
<p>I haven't found a solution to Windows problems yet, but I blacklisted a few modules in Ubuntu, namely by adding these lines in /etc/modprobe.d/blacklist.conf:<br />
blacklist rt2800pci<br />
blacklist rt2800usb<br />
blacklist rt2x00lib<br />
blacklist rt2x00pci<br />
blacklist rt2x00usb</p>
<p>Now Ubuntu is connecting like a champ.  Blazing fast, and reliable.  It seems to be using the rt 2860sta driver instead of the blacklisted ones now.</p>
<p>I originally found this information on the Ubuntu forums: http://www.uluga.ubuntuforums.org/showthread.php?t=1579053&page=2</p>
