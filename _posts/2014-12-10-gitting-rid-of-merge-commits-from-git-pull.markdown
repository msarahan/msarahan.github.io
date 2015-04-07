---
layout: post
status: publish
published: true
title: Gitting rid of merge commits from git pull
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 224
wordpress_url: http://t3hmikez0r.com/?p=224
date: '2014-12-10 20:40:28 -0800'
date_gmt: '2014-12-11 04:40:28 -0800'
categories:
- Nerd
tags: []
comments: []
---
<p>Some of you may know about git merging.Â  I'm learning.Â  I am contributing a bit of work to an open-source library, Scikit-Image.Â  One of the things you do out of politeness, to keep the commit history clean, is to rebase your (possibly many) commits into just one, so that the project's history shows your addition as truly one addition.Â  If, as in my case, your addition ends up taking a long time to get reviewed, you may end up in the situation where you need to pull in the upstream changes that have happened in the meantime.</p>
<p>Let's go through the process I used:</p>
<pre># Add upstream source to pull from:
git add remote upstream https://github.com/scikit-image/scikit-image.git</pre>
<pre># Merge upstream's changes into current branch
git pull upstream master</pre>
<pre># Check the git log
git log</pre>
<pre>commit 7bdcdeef0d4146d630d2937ba7b619cd23f233fd
Merge: b9c82d0 f822439
Author: Michael Sarahan &lt;msarahan@gmail.com&gt;
Date:Â Â  Sat Dec 6 20:27:20 2014 -0800

Â Â Â  Merge branch 'master' of https://github.com/scikit-image/scikit-image into PhaseCorrelation

commit b9c82d03f2c6c9584c834b05ffd5c3714248de4e
Author: Michael Sarahan &lt;msarahan@gmail.com&gt;
Date:Â Â  Mon Apr 28 08:03:15 2014 -0700

Â Â Â  Add subpixel-precision phase correlation function to feature module</pre>
<p>This is bad: an extra commit for the merge to update.Â  What's worse, I had already pushed my branch with this extra commit to github, so it showed up in the pull request.Â  Let's try to get rid of it:</p>
<pre>git rebase -i master</pre>
<p>(this contains all of the commits I brought in with the merge, but not the merge commit itself!)</p>
<p>How do I get rid of it, then?</p>
<pre>git reset --hard BRANCHNAME~1</pre>
<p>(Replace BRANCHNAME with the branch that you're currently working on.)</p>
<p>Now, a better way to bring in the updates from master:</p>
<pre>git pull --rebase upstream master</pre>
