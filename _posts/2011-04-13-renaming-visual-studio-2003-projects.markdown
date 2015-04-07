---
layout: post
status: publish
published: true
title: Renaming Visual Studio 2003 projects
author:
  display_name: mikez0r
  login: mikez0r
  email: msarahan@gmail.com
  url: http://
author_login: mikez0r
author_email: msarahan@gmail.com
author_url: http://
wordpress_id: 152
wordpress_url: http://t3hmikez0r.com/?p=152
date: '2011-04-13 06:03:39 -0700'
date_gmt: '2011-04-13 14:03:39 -0700'
categories:
- Nerd
tags:
- Nerd
- Digital Micrograph
- Programming
comments: []
---
<p>Edit, Nov 19, 2011</p>
<p>NOTE: this post is out of date.  Instead, please see the project here:<br />
<a href="https://github.com/SuperSTEM/DM_plugin_SerialComm" target="_blank">DM plugin - serial communication</a></p>
<p>This project uses relative paths everywhere, and sets output filenames dynamically based on the project name.  To use it, extract/sync the github repository to an installation of the DMSDK, then rename the project in Visual Studio.  You should be able to safely rename the project folder without breaking anything.</p>
<p>======================= Original post below ===================================</p>
<p>Yes, VS 2003 is out of date.  I use it to compile C++ extension plugins for Gatan Digital Micrograph (DM), which we use to control our microscopes and acquire/process data.  The SDK for DM is designed for Visual Studio 2003 (or older).</p>
<p>Part of the problem of doing something that very few others do is that the documentation is usually poor.  This is very much the case with the SDK.</p>
<p>Here was my problem:</p>
<ul>
<li>I don't know how to create a new project and have it compile.  The SDK is sufficiently complicated and different from any standard Visual Studio project that it is difficult to take this path.</li>
<li>I don't know how to rename my VS 2003 project files without breaking the project.  Thus, I am unwilling to distribute the source code to my project, since it is named something completely unrelated.</li>
</ul>
<p>Here's my solution:</p>
<ul>
<li>In Windows Explorer:</li>
<ol>
<li>Rename the project folder in the filesystem.</li>
<li>Rename the .sln and .rc files in the project folder.  DO NOT rename the .vcproj file.</li>
</ol>
<li>In VS2003:</li>
<ol>
<li>Open the project by picking the .sln file to open.</li>
<li>Rename the project in the solution explorer (right click, and select rename)</li>
<li>Select the project in the solution explorer, and then click the File menu.  Select Save as... and enter the new filename for your .vcproj file.  You can now delete the old .vcproj file from the folder.</li>
<li>For old source files to be excluded, right click them in the solution explorer, and click remove.</li>
<li>For new files to be included, right click on the project or folder in the solution explorer, and select Add... -> Add existing item...</li>
<li>In the project properties (right click the project, and select properties):</li>
<ol>
<li>Under C/C++, pick the Precompiled Header options, and rename the Precompiled header file appropriately (not entirely necessary, this is a cosmetic change since this file gets (re)generated automatically when necessary)</li>
<li>Under Linker, in the General options, change the Output File.</li>
<li>Under Linker, Debugging: update the "Generate Program Database File" option</li>
<li>Under Linker, Advanced: update the "Import Library" option</ol>
</li>
</ol>
</ul>
<p>Now you should no longer have any files popping up with the old name.</p>
<p>Good luck with your DM plugins and renamed VS 2003 projects!</p>
