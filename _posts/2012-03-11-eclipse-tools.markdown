---
author: milocasagrande
comments: true
date: 2012-03-11 17:29:58+00:00
layout: post
link: https://www.milo.name/2012/03/11/eclipse-tools/
slug: eclipse-tools
title: Eclipse Tools
wordpress_id: 57
categories:
- Development
tags:
- development
- eclipse
- tools
---

This is more a brain-dump kind of post for me, so I do not forget, every time I need to re-install Eclipse for whatever reasons, to install the plugins I need the most (and where to find them) or to tweak it a little bit. Since my daily work is more Java-based, the tools I use are Java-centric.

### Bash Tool

I tend to write a lot of shell code too, maintenance scripts for the servers or for repetetive tasks, and since I'm mostly working with Java and Eclipse, I needed something that could decently handle bash files inside Eclipse.

[ShellEd](http://sourceforge.net/projects/shelled) comes to the rescue (the website is pretty basic, with not a lot of info). I didn't look deeply into other shell plugins for Eclipse, but this one works nicely.

To use it, it is necessary to install also the LinuxTools Eclipse plugin (from [here](http://www.eclipse.org/linuxtools/downloads.php)). The only necessary part of that set of tools, if C/C++ development and the other Linux integrations are not necessary, is the man pages viewer. ShellEd is able to present you with man pages of the shell commands in a hoover-help fashion (even if I find it tad slow).

To install, download the [zip file](http://sourceforge.net/projects/shelled/files/latest/download), and from _Help → Install New Software → Add_, use the _Archive_ button to install it.

### Editing Sessions

At work I might be working or looking on different projects, with different set of files each, and I tend to work focused on the task at hand, trying not to pollute the screen with other distractions, even in the terms of files from another project. I was looking for an easy way to save and restore the "editing session", the open files.

I find the _Extended VS Presentation_ plugin to be very useful in this (info [here](http://andrei.gmxhome.de/skins/index.html)).

Pretty simple to install in Eclipse via the "_Help → Install New Software_", and then pasting in the "_Work with_" text-box this URL: http://andrei.gmxhome.de/eclipse/

### Python

From time to time I also write some Python code, and as for shell code, I prefer to not move from the environment I'm used. For Eclipse there is a powerful plugin for Python: [PyDev](http://pydev.org/). [Installation instructions](http://pydev.org/manual_101_install.html) are very well written.

### Static Analysis

Other tools that for me are a must have, are a set of static analysis tools. The more useful:

  * [PMD](http://pmd.sourceforge.net/): Eclipse instructions are [here](http://pmd.sourceforge.net/eclipse/);

  * [FindBugs](http://findbugs.sourceforge.net/): installable via the Eclipse Market;

  * [CodePro Tools](http://code.google.com/intl/en/javadevtools/codepro/doc/index.html): comes from Google, and it is more than a static code analysis tool: can calculate code metrics, is a code coverage tool, has JUnit integration and can generate unit tests automatically. Can't live without this.

### Speed Eclipse a Little Bit

And this is my Eclipse configuration file, I find Eclipse a little bit faster at startup (make a copy of your old one if you want to use this!):

[gist id=2017130 file=eclipse.ini]
