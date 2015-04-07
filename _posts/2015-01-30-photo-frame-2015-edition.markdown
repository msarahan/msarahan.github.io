---
layout: post
status: publish
published: true
title: Photo Frame (2015 edition)
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 227
wordpress_url: http://t3hmikez0r.com/?p=227
date: '2015-01-30 20:40:09 -0800'
date_gmt: '2015-01-31 04:40:09 -0800'
categories:
- Nerd
tags:
- photo frame
comments: []
---
<p>Newest approach to photo frames: Raspberry Pi.  There's also an excellent wallpaper changer called <a href="http://peterlevi.com/variety/">Variety, by Peter Levi</a>.  I wrote directions originally at Peter Levi's blog: <a href="http://peterlevi.com/variety/how-to-install/">http://peterlevi.com/variety/how-to-install/</a></p>
<p>I have recently purchased a Raspberry Pi B+, which might be more updated than the RPi I originally used (a model B from last year sometime.)  For my reference, here are directions from installing on the B+.</p>
<h1>Complete directions for posterity's sake:</h1>
<p>1. Install dependencies:<br />
<code>sudo apt-get install gir1.2-notify-0.7 python-configobj python-pyexiv2 python-pycurl gir1.2-gtk-3.0 python-dbus gir1.2-pango-1.0 gir1.2-glib-2.0 python-imaging python-cairo gir1.2-gdkpixbuf-2.0 python-bs4 gir1.2-webkit-3.0 yelp imagemagick python-lxml gir1.2-appindicator3-0.1</code></p>
<p>2. Install bzr:<br />
<code>sudo apt-get install bzr</code></p>
<p>3. Checkout from the repository:<br />
<code>bzr branch lp:variety</code></p>
<p>4. Run<br />
<code>~/variety/bin/variety</code><code><br />
</code></p>
<p>5. Edit Variety preferences to enable start when RPi starts up</p>
<p>6. Edit .config/autostart/variety.desktop to fix path (<code>Exec=sh -c "/home/pi/variety/bin/variety"</code>)</p>
<p>7. Install unclutter to hide the mouse cursor:<br />
<code>sudo apt-get install unclutter</code></p>
<p>8. Run unclutter at startup and disable screen blanking:</p>
<p><code>sudo nano /etc/xdg/lxsession/LXDE-pi/autostart</code><br />
- delete line that starts xscreensaver<br />
- Add 4 lines:</p>
<p><code>@unclutter<br />
@xset s off<br />
@xset -dpms<br />
@xset s noblank<br />
</code></p>
<p>9. Reboot and enjoy</p>
<p>References:</p>
<ul>
<li><a href="http://peterlevi.com/variety/how-to-install/">http://peterlevi.com/variety/how-to-install/</a></li>
<li><a href="http://www.raspberrypi.org/forums/viewtopic.php?f=91&amp;t=57552">http://www.raspberrypi.org/forums/viewtopic.php?f=91&amp;t=57552</a></li>
</ul>
