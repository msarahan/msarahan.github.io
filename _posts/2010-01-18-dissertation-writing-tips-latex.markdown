---
layout: post
status: publish
published: true
title: 'Dissertation writing tips: Latex and Mendeley'
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 116
wordpress_url: http://t3hmikez0r.com/2010/01/18/dissertation-writing-tips-latex/
date: '2010-01-18 23:57:02 -0800'
date_gmt: '2010-01-19 07:57:02 -0800'
categories:
- Uncategorized
- Nerd
tags:
- Nerd
- dissertation
- latex
comments: []
---
<p>Some odd notes of potential usefulness as I stumble through dissertation writing:</p>
<ul>
<li>Proper figure numbering is accomplished by including the \label{} command inside the \caption{caption} command.  Otherwise, it catches the section number...</li>
</ul>
<ul>
<li>Mendeley is great for managing references.  Set the web importer up as a bookmark in the bookmark toolbar.  It can grab references from Google Scholar, Google books, and many others.  I find that the direct grabs from a Google Scholar search are incomplete - where possible click the link through to the page with the abstract, and import the article from there.</li>
</ul>
<ul>
<li>Store your articles with Mendeley's web storage to keep them in sync across multiple computers.  To start storing them, right click your "All Documents" collection, then "Edit settings" (Why isn't there any reference to this in Mendeley's program settings?  I had a hell of a time finding this.)</li>
</ul>
<ul>
<li>\ref and \cite are very different Latex commands.  If a bibtex reference refuses to show up, you probably  tried to cite it using \ref, rather than \cite.  \ref is for references defined by \label.</li>
</ul>
<p>And... my theme here apparently has a problem showing bulleted and numbered lists...</p>
