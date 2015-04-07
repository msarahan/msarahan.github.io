---
layout: post
status: publish
published: true
title: OpenCV image registration
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 97
wordpress_url: http://t3hmikez0r.com/2009/10/13/opencv-image-registration/
date: '2009-10-13 08:51:32 -0700'
date_gmt: '2009-10-13 16:51:32 -0700'
categories:
- Uncategorized
tags:
- Nerd
comments:
- id: 68
  author: Linda Rawson
  author_email: linda.rawson@sensorytech.net
  author_url: http://www.sensorytech.net
  date: '2009-10-13 14:37:36 -0700'
  date_gmt: '2009-10-13 22:37:36 -0700'
  content: "Mike,\r\n\r\nCould you contact me about this blog that you wrote?  We
    are very interested in the work you have been doing.\r\n\r\nThanks,\r\nLinda Rawson"
- id: 77
  author: Christof
  author_email: christofb@gmx.de
  author_url: http://NONE
  date: '2009-11-11 10:40:02 -0800'
  date_gmt: '2009-11-11 18:40:02 -0800'
  content: "Hi,\r\nI really like your idea.\r\nI am really interested in your solution
    and try to implement it like you did. Could you somehow send me your whole sources?\r\n\r\nRegards,\r\nChristof"
- id: 10823
  author: Epifania
  author_email: vickeyblankenship@t-online.de
  author_url: https://www.facebook.com/permalink.php?story_fbid=
  date: '2015-02-03 21:45:28 -0800'
  date_gmt: '2015-02-04 05:45:28 -0800'
  content: indah, saya hanyut penjelasannya
---
<p>This is more a note to self than anything else, but if you find it useful, hooray!</p>
<p>I'm trying to register images for school.  There's a neat trick to get rotation & scale roughly aligned, without doing any kind of brute forcing (which is really important, because my images can be any angle offset from one another).  You take the log-polar transform of each image, and then cross-correlate the two transformed images.  The distance from the center to the cross correlation maximum along the Y axis tells you the rotation, and the same on the X axis tells you the scale (on a logarithmic scale).  The end result is that you can avoid the local alignment maxima associated with brute forcing, and save a whole lot of time in the process.</p>
<p>However, it doesn't work perfectly for me yet.  Here's a few steps I've taken to improve it:</p>
<p>1. Pad the image that you're going to match the template on.<br />
Python with ctypes_opencv:</p>
<p>  pad_img=ocv.cvCreateImage(ocv.cvSize(cropWidth*3,cropHeight*3),<br />
    expIPLimg.depth,expIPLimg.nChannels)<br />
  offset=ocv.cvPoint(cropWidth,cropHeight)<br />
  ocv.cvCopyMakeBorder(expLP, pad_img, offset,<br />
	ocv.IPL_BORDER_CONSTANT, ocv.cvAvg(expLP))</p>
<p>2. Do not cross-correlate the entire template to match.  Instead, match only the central strip.  There's plenty of good stuff to match there, and you avoid the correlation penalties of having your template overlap with the padding.  If you don't do this, then the scale correction possible will be limited.</p>
<p>  resultWidth = pad_img.width - refLP.width/2 + 1<br />
  resultHeight = pad_img.height - refLP.height + 1<br />
  result = ocv.cvCreateMat(resultHeight,resultWidth,ocv.CV_32F)<br />
  ocv.cvSetImageROI(refLP,ocv.cvRect(refLP.width/4,<br />
  	0, refLP.width/2, refLP.height))<br />
  ocv.cvMatchTemplate(pad_img,refLP,result,ocv.CV_TM_CCOEFF_NORMED)</p>
