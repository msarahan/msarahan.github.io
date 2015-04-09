---
layout: post
status: publish
published: true
title: Fixed width string formatting in python
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 83
wordpress_url: http://t3hmikez0r.com/?p=83
date: '2009-02-25 22:23:14 -0800'
date_gmt: '2009-02-26 05:23:14 -0800'
categories:
- Uncategorized
- Nerd
tags:
- Nerd
comments:
- id: 232
  author: "ECAE &#8212; Shopex\x90 &raquo; [Denny --
    ] Python"
  author_email: ''
  author_url: http://blog.ec-ae.com/?p=434
  date: '2011-12-21 07:34:33 -0800'
  date_gmt: '2011-12-21 15:34:33 -0800'
  content: "[...] printf http://t3hmikez0r.com/2009/02/25/fixed-width-string-formatting-in-python/
    Fixed width string formatting in [...]"
---
<p>I wanted to make a nice, pretty text file from some log info, but python didn't want to cooperate with string formatting.</p>
<p>I was trying something like this:<br />
f=open('file','w')<br />
f.write('%-10s' %string)</p>
<p>At the interactive prompt, the equivalent print command would give the desired result.</p>
<p>I got it to work by replacing f.write() with<br />
print >> f, mystring.ljust(10)</p>
<p>This code has the same net result of printing to the file, but it actually does the spacing properly.</p>
<p>This thread gave me the hint I needed, though it looks like the poor guy never resolved his issue - he should have tried the print suggestion.</p>
<p>http://bytes.com/groups/python/25205-using-string-ljust-try-hold-fixed-width#links</p>
