---
layout: post
status: publish
published: true
title: Python with Wing IDE
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 197
wordpress_url: http://t3hmikez0r.com/?p=197
date: '2012-11-05 18:49:14 -0800'
date_gmt: '2012-11-06 02:49:14 -0800'
categories:
- Uncategorized
tags: []
comments:
- id: 281
  author: Stephan Deibel
  author_email: support@wingware.com
  author_url: http://wingware.com/
  date: '2012-11-06 06:39:23 -0800'
  date_gmt: '2012-11-06 14:39:23 -0800'
  content: "A couple of notes that might be useful:  \r\n\r\n(1) I suspect crashing
    is coming from GTK binary incompatibilities; on 64-bit Linux Wing runs using the
    system-provided GTK.  This used to work but seems more of a problem on recent
    Ubuntu (probably also dists).  The work-around is to install 32-bit Wing (which
    can still work w/ 64-bit Python) as described at the end of http://wingware.com/doc/install/linux-installation-detail
    -- our solution for this is going to be Wing 5, which doesn't use GTK.  Sorry
    about this problem!\r\n\r\n(2) To get back to an earlier location before goto-definition
    or whatever, use the forward/back buttons at top left of the editor area.\r\n\r\n(3)
    You do need to restart after modifying code in an editor and saving unless your
    app has a way to reload that code, which in most cases it won't.  There's no good
    way to do general purpose reload from the debugger itself (runs into some issues
    in how CPython is designed, as well as just the hairy reality of doing this.  For
    more advanced users there is this add-on that allows some limited moving of program
    counter:  http://wiki.wingware.com/DebugMoveProgramCounter\r\n\r\n(4) Also check
    out the Debug Probe if you haven't already.\r\n\r\nIn general if you run into
    serious problems like crashing please always email support@wingware.com!\r\n\r\nThanks
    for posting this!\r\n\r\nStephan Deibel\r\nWingware"
---
<p>I have been generously granted a Wing IDE license for my hobby programming on Analyzarr ( http://www.github.com/msarahan/analyzarr ).Â  It has taken me a while, but I owe this review to the generosity of WingWare.</p>
<p>First off, I have been programming python for several years now.Â  I have always used only a combination of a text editor and an interactive prompt (IPython, especially). I'm writing this review as my first experience with a Python IDE.</p>
<p>In my new job, I have been using visual studio for C++ programming.Â  I have gotten used to handy things like debugging tools.Â  I'm sure there are ways to do this in Python, but Visual Studio makes it, well, visual.Â  In IPython, I rather used the pdb magic call to turn on automatic pdb calling.Â  It was of mixed use, probably because I didn't know how to use it.Â  I was very excited to try Wing's debugging facilities.</p>
<p>Before I get ahead of myself, let me start where I should start, and that is first with a description of my system, followed shortly by the tutorial.</p>
<p>I have Ubuntu 12.04 x64, running on an AMD platform.Â  I am using Enthought's EPD distribution, to which I subscribe (it is well worth it.)Â  That gives me Python 2.7, and several up-to-date scientific libraries.</p>
<p>Tutorial:</p>
<ul>
<li>A lot of effort obviously went into this.Â  It is very detailed, and it walks you through nicely.</li>
<li>I encountered a crash when setting my python path.Â  I repeated it twice, then gave up.Â  I don't use pythonpath anyway.Â  Rather, I generally install my code in development mode using something like 'pip install -e ./' from my source folder.Â  I hope this won't be a problem down the road...</li>
<li>Completion/"Source Assistant" - this thing is great!Â  Having the docstrings right next to the editor, along with links to function declarations?Â  This is fantastic!Â  I'm left wishing for a way to jump back to the part I was just editing, before I clicked the link to jump to a function definition</li>
<li>Debugging in the tutorial: I crashed again.</li>
<li>Debugging, attempt 2: OK, now I encounter a problem with the path_example import.Â  There's a helpful comment explaining that this won't work if you don't have the PYTHONPATH set from earlier in the tutorial.Â  Very nice of them to not let users wonder about this!</li>
<li>Well, I'd really like to set that PYTHONPATH, but again, I'm bombing out.Â  I'm resorting to just copying the path_example.py file from subfolder into the folder with example1.py.</li>
<li>OK, on with debugging.Â  Breakpoints.Â  Yes.Â  This often exactly what I want when I'm trying to figure out an annoying bug.Â  But wait, things get better</li>
<li>When things go wrong in Python, you get a traceback.Â  It tells you the locations in all of the files up the call chain where things went wrong.Â  It's very useful for tracking down bugs, but here's the hitch - if you have a bug in your code that is messing up someone else's code, then the last error is not obvious.Â  Wing really shines here - in its exceptions view, you can navigate that whole call stack, jumping to the source where the exception occurred.Â  Very nice!</li>
<li>Debugging just gets better!Â  You can enter code at breakpoints, up to even redefining functions.Â  As the tutorial states, when a bug depends on program state, you don't always want to start from the beginning. Instead, you can fix the bug, test it, and move on.Â  All without restarting the potentially lengthy process leading up to this point.</li>
<li>Lots of shortcuts for matching parentheses, jumping around, and generally getting lost in unimaginably useful ways.</li>
</ul>
<p>Wing looks like a great environment, and I'm eager to get my feet wet.Â  I might post again soon on my experience using it to actually replace emacs/IPython as my development platform.</p>
