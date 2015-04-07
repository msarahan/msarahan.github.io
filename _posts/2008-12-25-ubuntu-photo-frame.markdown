---
layout: post
status: publish
published: true
title: Ubuntu photo frame
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 63
wordpress_url: http://t3hmikez0r.com/?p=63
date: '2008-12-25 01:42:06 -0800'
date_gmt: '2008-12-25 08:42:06 -0800'
categories:
- Nerd
tags: []
comments:
- id: 59
  author: snypez
  author_email: tim@lavidamassage.com
  author_url: http://www.lavidamassage.com
  date: '2009-02-18 09:59:41 -0800'
  date_gmt: '2009-02-18 16:59:41 -0800'
  content: Just wondering if you wouldn't mind posting more in depth as to how you
    upgraded perl from the debian repo as I am having the same problem. I have done
    some research and many people say this is a very bad idea but I am a reckelss
    individual so I don't really care. Current thread on this issue can be found @
    http://guide.ubuntuforums.org/showthread.php?p=6675175 .
- id: 61
  author: mikez0r
  author_email: msarahan@gmail.com
  author_url: http://
  date: '2009-02-21 14:48:10 -0800'
  date_gmt: '2009-02-21 21:48:10 -0800'
  content: "Easiest is to download the updated perl package directly from debian,
    and then force it in.\r\n\r\nDL it from here:\r\nhttp://packages.debian.org/sid/perl\r\n\r\nand
    then force it in with\r\n\r\ndpkg --install\r\n\r\nMight have to force it somehow.
    \ I can't remember.  Check the dpkg man page."
---
<p>Digital picture frames are neat little gizmos - especially for showing pics to my parents, who are rarely, if ever, inclined to poke around flickr (or anything much beyond their email).Â  I have had various setups for a while using an old laptop.Â  At first, I used Windows, because the wifi drivers for Linux were either missing for my card, or inadequate (non-functional, or locked up computer frequently).Â  I have finally gotten a card that agrees with Linux (the Intel 2200BG MiniPCI), and the computer is now up and running with Xubuntu.Â  Many options are out there for picking particular sets, or photos by interestingness, but I wanted simply a way to download my whole photostream and allow a screensaver to meander the collection.Â  Not all of my photos are interesting, but they have other personal value of interest to parents.</p>
<p>The synopsis of what I do:<br />
- Use flickrfs to mount my photos on the drive<br />
- rsync to copy photos from flickrfs to local drive<br />
- cron to run photo update scripts nightly</p>
<p>To do this yourself,</p>
<ol>
<li>Get flickrfs - on Ubuntu/Xubuntu 8.04 and 8.10, this can be accomplished with<br />
apt-get install flickrfsÂ  (sudo as necessary)</li>
<li>Make 2 folders - one to mount flickrfs to, and another to store your pictures locally.Â  Make sure you have write access to both of them (obviously)</li>
<li>Mount the flickrfs filesystem to the folder you created for it.Â  This is as simple as the command<br />
flickrfs /PATH/TO/YOUR/DESIRED/MOUNTPOINT</p>
<p>After running that command, a web browser will open for you to authorize flickrfs to access your account.Â  Eventually, the command line window will spit out something about updating your sets, and tell you when it's done.</li>
<li>You should now have 2 folders in your flickrfs mount point - sets and meta</li>
<li>If you have the 2 folders, create a folder named "stream" in the flickrfs mountpoint. If you don't have the 2 folders and you create the stream directory, fuse will complain about a non-empty directory.Â  The flickrfs mount point must be empty until it (flickrfs) puts stuff there.</li>
<li>Wait 5-10 minutes for flickrfs to populate the stream folder</li>
<li>rsync to copy files from the flickrfs/stream/ folder to your local pictures folder.</li>
</ol>
<p>If anyone finds it useful, here's the script that I have cron run to update my local Pictures directory with the contents of my photostream.Â  There's also a bit in there to clean up empty files.Â  rsync seems to be not quite perfect with flickrfs, and I accumulated a few empty jpg's that confused the screensaver.</p>
<p><a href="http://t3hmikez0r.com/wp-content/uploads/2008/12/flickr-update.sh">flickr-update</a></p>
<p>I display the pictures using GLslideshow, which is standard with xscreensaver.Â  I replaced gnome-screensaver with xscreensaver, as configuration of xscreensaver is easier.Â  To ensure that xscreensaver is always reading a fresh set of photos, I kill it and restart it nightly (cron is really useful!).Â  I did have to tell XFCE to start xscreensaver at startup - it isn't a completely automatic drop-in replacement for gnome-screensaver.Â  To point xscreensaver at your local pictures directory, check the advanced tab in the upper right, and change the folder where it looks for pictures.</p>
<p>Side note: The Perl installation for Ubuntu 8.10 has a bug with xscreensaver.Â  It dumps yellow text onscreen, something about a constant being changed.Â  I fixed this by adding a debian sid repository to my third party software, and using the Perl version from there, since it's more up to date.Â  It fixed the yellow text problem for me.Â  The older this post gets, the less likely this will be an issue for you - I imagine the Ubuntu people will update this soon.</p>
