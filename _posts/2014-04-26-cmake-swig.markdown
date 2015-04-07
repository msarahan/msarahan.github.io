---
layout: post
status: publish
published: true
title: CMake + SWIG
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 207
wordpress_url: http://t3hmikez0r.com/?p=207
date: '2014-04-26 08:20:54 -0700'
date_gmt: '2014-04-26 16:20:54 -0700'
categories:
- Uncategorized
tags: []
comments: []
---
<p>I was beating my head against CMake + SWIG, trying to get started, but for some reason, I was never actually getting SWIG to generate its intermediates. If I specified things manually on a command line, it worked.</p>
<p>Here was my problem:<br />
I had my SWIG input with a .swg extension, rather than .i - I found the .swg extension to be a more clear indicator that I was using SWIG, but I guess it confuses CMake.</p>
