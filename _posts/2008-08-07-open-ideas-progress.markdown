---
layout: post
status: publish
published: true
title: Open ideas & progress
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 50
wordpress_url: http://t3hmikez0r.com/?p=50
date: '2008-08-07 13:55:54 -0700'
date_gmt: '2008-08-07 20:55:54 -0700'
categories:
- Nerd
- Philosophical musings
tags: []
comments: []
---
<p>I've been at a conference in New Mexico since last Tuesday, and I've had lots of interesting encounters and discussions.Â  One today was really frustrating though, so I'm writing about it.Â  I met a seemingly brilliant man who has come up with a new way to reconstruct 3D models from 2D projections.Â  He does it very quickly and with fewer projections than I thought possible, and with very good results.Â  He asked me what I was doing, after I gave him some details on GPU programming.Â  I don't really have a well-defined plan yet, but I think I'd like to make it easier and more accessible for anyone to do these 3D reconstructions.Â  There are a number of programs, but most of them are variously counterintuitive, incomplete, poorly documented, buggy, etc.Â  I would like to create a framework for doing the image processing and reconstruction, and do it in such a modular way that it would be easy for anyone else to add to it in the future.Â  The best (non-commercial) program that I know of is IMOD, but it is not modular this way.</p>
<p>Well, this guy has developed a fairly complete package for all the steps of reconstruction, but he's keeping it under wraps.Â  The way that he wants it to work is for people to send him data (2D images), and he'll reply with their 3D model.Â  That's a black box.Â  I hate black boxes.Â  They can't be trusted, especially in science.Â  If you don't know how someone is doing something, then their result can't be trusted.Â  I don't care how good it looks or how well it matches with the 2D data.Â  Open Source software is the obvious opposite of this, but I don't think that everything has to be open source.Â  It should, however, be completely clear what a program is doing, to ensure that it is scientifically valid.Â  He did present a poster, and he vaguely details his methodology, but he intends to keep the detailed workings secret.</p>
<p>On the other hand, if everything was open source, I'm convinced that progress would be much faster.Â  There would be so much less duplication of work.Â  America's economic model is obviously not compatible with everyone working together, and I don't know of any other economy that would be totally compatible.Â  It is a pipe dream, but it sounds nice.Â  In this particular example, if everyone would work together, rather than 15 different labs all creating their own software, then perhaps one or two truly high-quality software packages could have been developed by now.Â  I don't pretend to know how you'd split up funding or even put in a proposal for that sort of thing, but it seems like a more logical solution to a problem that we all face, and a problem that is far more general than 3D reconstruction software.Â  Linux has proven a lot of things possible, and we'll see over the course of the next 10-20 years if my ideas of open development speeding beyond closed source actually come true.</p>
