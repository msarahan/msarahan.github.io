---
layout: post
status: publish
published: true
title: Number patterns
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 179
wordpress_url: http://t3hmikez0r.com/?p=179
date: '2012-07-29 18:48:04 -0700'
date_gmt: '2012-07-30 02:48:04 -0700'
categories:
- Nerd
- Needlessly Cerebral
tags: []
comments: []
---
<p>I came across a cheesy joke on the internet today. It went along the lines of "pick a number between 1 and 10, and this will automatically determine your favorite movie."</p>
<p>The steps were:<br />
1. Multiply your number by 3.<br />
2. Add 3.<br />
3. Multiply this sum by 3.<br />
4. Add together the digits of the product.</p>
<p>The movie choices were all mainstream, except #9, which was some bizarre pornographic bundle of inappropriateness. I ran through the math with #7. ((7*3)+3)*3 = 72. Summing digits = 9. Low and behold, my favorite movie was the bizarre porno. I chose another number - 6 - was it an unfortunate guess the first time? ((6*3)+3)*3 = 63. Again, 9. Again, porno.</p>
<p>So, I'm now assuming that no matter what you choose, you end up a pervert. Whatever. The more curious thing is the number pattern. How do you always end up with 9? After some clumsy attempts at algebra (the digit summing threw me off), I realized that all possible number choices were multiples of 9. Then I noticed a more interesting pattern - for every single multiple of 9 between 1 and 10, the digits sum to 9. Try it.</p>
<p>OK, that was interesting. I wondered if the other numbers had this property. Let's look at 8.</p>
<p>1* 8 = 8 (sums to 8)<br />
2* 8 = 16 (sums to 7)<br />
3* 8 = 24 (sums to 6)<br />
4* 8 = 8 (sums to 5)<br />
5*8 = 40 (sums to 4)<br />
6*8 = 48 (sums to 12)<br />
7*8 = 56 (sums to 11)<br />
8*8 = 64 (sums to 10)<br />
9*8 = 72 (sums to 9)<br />
10*8 = 80 (sums to 8)</p>
<p>So, we have a series that decreases by one each time, resetting at 6, and ending up back at 8 when the multiple is 10. Much more interesting than 9, in my opinion.</p>
<p>How about 7?</p>
<p>1*7 = 7 (sums to 7)<br />
2*7 = 14 (sums to 5)<br />
3*7 = 21 (sums to 3)<br />
4*7 = 28 (sums to 10)<br />
5*7 = 35 (sums to 8)<br />
6*7 = 42 (sums to 6)<br />
7*7 = 49 (sums to 13)<br />
8*7 = 56 (sums to 11)<br />
9*7 = 63 (sums to 9)<br />
10*7 = 70 (sums to 7)</p>
<p>7 is even cooler - it decreases by 2 each time, and resets itself predictably every 3 multiples (excluding 10.) 10 again ends up the same (noticing a trend here? - why does the trend make sense?)</p>
<p>My attention span is over for now, but I thought I'd share these interesting number patterns. If any math nerds would like to point me to a wikipedia page on these patterns, I'd be grateful.</p>
<p><strong>Edit</strong> - lying in bed, I could not stop thinking about these patterns. 9 is even more magical than I realized. The digits of any multiple of 9 will ultimately sum to 9. I was initially concerned about the number 10 in the problem. (3*10+3)*3 = 99. Summing those isn't 9! However, the sum of their sums (18) is 9! This property extends to any and every multiple of 9. Moreover, the number of 18's in the first sum increases by one per multiple of 10. Once you get into the hundreds, you get one additional 27 in the series for 100-1000 for each multiple of 100 (1 for 100-200, 2 for 200-300, etc.) . These all still sum to 9!</p>
<p>Here's a python function you can play with to look at these sequences:</p>
<blockquote>
<pre>def stringsum (number):
    n=str(number)
    s=0
    for char in n:
        s+=int(char)
    return s</pre>
</blockquote>
<p>It is best used with a list comprehension, like this (multiples of 8, from 100 to 200, in intervals of 1):</p>
<blockquote>
<pre>[stringsum(x) for x in numpy.arange(100, 200, 1)*8]</pre>
</blockquote>
<p>To verify that digits totally sum the way I claim, let's make that function recursive:</p>
<blockquote>
<pre>def stringsum (number):
    n=str(number)
    s=0
    for char in n:
        s+=int(char)
    if len(str(s))!=1:
        return stringsum(s)
    return s</pre>
</blockquote>
<p>Here, you can see that for 8, the sequence is a count by one through the digits, looping from 1 to 9.</p>
<p>For 7, it is similar, except the count is by two, and we alternate between even and odd (counting down from odd until we pass 0, then reset and count evens.)</p>
<p>6 counts in 3's. It only ever has 3, 6, and 9 in its sequence. As you might expect by now for 5, it counts by 4, and behaves like 7 in that it alternates between even and odd sequences.</p>
<p>4 reverses the trend. It counts by 4. In turn, 3 counts by 3, and so on. Such interesting and beautiful symmetry!</p>
