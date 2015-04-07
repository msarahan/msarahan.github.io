---
layout: post
status: publish
published: true
title: OS X 10.6 problems & fix
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 103
wordpress_url: http://t3hmikez0r.com/2009/12/16/os-x-10-6-problems-fix/
date: '2009-12-16 22:59:59 -0800'
date_gmt: '2009-12-17 06:59:59 -0800'
categories:
- Uncategorized
tags:
- Nerd
comments: []
---
<p>Oh boy, was I seething at Apple after upgrading to 10.6.  It seemed like just about everything broke.  All of my Python development stuff went to hell in a handbasket (a stylish, well-designed handbasket).  My 600$ (educational) copy of the Adobe CS3 Design pack would not even install.  To boot,  X11 did not work, so I couldn't even use trusty old NXclient to remote desktop on my linux box.</p>
<p>I'm not sure why, but I didn't bother searching for anyone with similar problems at the time.  After going through the trouble to revert to 10.5, I did that search, and found all kinds of exactly similar problems, mostly caused by cruft from the old system.  After a fresh OS X 10.6 install, things are in much better shape.  Yes, there are other ways to clean up the cruft, but fresh installs feel so nice.  CS3 still won't install, but I can live with Inkscape and the GIMP.</p>
<p>Long story short: OS X is not the bulletproof OS that it is often advertised as, but it's also not as bad as I thought.</p>
<p>Oh, one quirk:<br />
Everyone mentions how much space 10.6 frees up on their hard drive.  That's nonsense.  It may use a tiny bit less space, but the real "increase" in hard disk space comes because they switched to calling kilobytes 1000 bytes, rather than 1024 bytes (and MB are 1000 KB, and so forth).  Because it divides the total number of bytes by an accordingly smaller number, you end up with a "bigger" hard drive.  This has long been what the hard drive manufacturers do, but it's awfully shady and very arbitrary for Apple to make that switch now.</p>
