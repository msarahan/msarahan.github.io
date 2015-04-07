---
layout: post
status: publish
published: true
title: Installing OpenCV with EPD on Ubuntu 11.04
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 154
wordpress_url: http://t3hmikez0r.com/?p=154
date: '2011-05-18 07:37:40 -0700'
date_gmt: '2011-05-18 15:37:40 -0700'
categories:
- Uncategorized
tags:
- Nerd
- Ubuntu 11.04
- Linux
- Python
- OpenCV
comments: []
---
<p>Quick note to self on getting OpenCV up on Linux with EPD.</p>
<p>When you run cmake (ccmake for the curses gui), toggle the advanced options.  The python includes, binary, and lib directories are options that only show as advanced options.  Change these to reflect your location for EPD.  After running make, the cv.so library that python gets its functions from gets installed by default to /usr/local/lib/python2.7/site-packages/cv.so.  Copy it instead to EPD_INSTALL_DIR/lib/python2.7/site-packages.  You should be good to go, now.</p>
<p>Also, one other problem:<br />
Ubuntu 11.04 has pulled the old switcheroo on library locations.  If you've installed all the dev versions of the necessary libraries (libjpeg, libpng, libtiff, libzip were my problem libraries), you also need to create symlinks from their new locations to the locations that OpenCV's make/CMake is expecting to find them:</p>
<p>ln -s /usr/lib/x86_64-linux-gnu/libjpeg.so /usr/lib/libjpeg.so<br />
ln -s /usr/lib/x86_64-linux-gnu/libpng.so /usr/lib/libpng.so<br />
ln -s /usr/lib/x86_64-linux-gnu/libtiff.so.4 /usr/lib/libtiff.so<br />
ln -s /usr/lib/x86_64-linux-gnu/libz.so /usr/lib/libz.so</p>
<p>This hint courtesy of:<br />
<a href="http://www.nigeldunn.com/2011/05/14/ubuntu-11-04-libjpeg-so-libpng-so-php-installation-issues/">http://www.nigeldunn.com/2011/05/14/ubuntu-11-04-libjpeg-so-libpng-so-php-installation-issues/</a></p>
