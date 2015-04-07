---
layout: post
status: publish
published: true
title: Linux photo frame revisited
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 175
wordpress_url: http://t3hmikez0r.com/?p=175
date: '2012-04-07 19:37:25 -0700'
date_gmt: '2012-04-08 03:37:25 -0700'
categories:
- Uncategorized
tags:
- Nerd
- ubuntu
- photo frame
comments: []
---
<p>Thanks to a hard drive crash, I'm recreating the Ubuntu-based photo frame for my parents.</p>
<p>Here's the setup this time:<br />
- Lubuntu 11.10 as the base<br />
- Wally as the wallpaper changer ( http://www.becrux.com/index.php?page=projects&amp;name=wally )<br />
- fluxbox as the window manager, replacing LXDE. I like LXDE, but Wally can't change the wallpaper under LXDE.<br />
- unclutter to hide the cursor when it is idle<br />
- a few customizations to the fluxbox startup:</p>
<p>in ~/.fluxbox/startup:<br />
add the following lines just before the "exec fluxbox" line:</p>
<p>xset -dpms<br />
xset s off<br />
unclutter &amp;<br />
wally &amp;</p>
<p>Those turn off the auto-power saving monitor feature, and disable the screensaver, hide the mouse cursor when idle, and finally starts wally at startup.</p>
<p>- one customization to make fluxbox load instead of LXDE:<br />
in /etc/lxdm/default.conf, change:<br />
session=/usr/bin/startlubuntu<br />
to<br />
session=/usr/bin/startfluxbox</p>
<p>Note: the wally icon does not show up in the system tray this way. If you start wally manually from the command line and save your settings, they stick.</p>
