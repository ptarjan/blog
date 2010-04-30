--- 
permalink: /2009/06/debugging-django.html
layout: post
title: Debugging django
tags: 
- django
- debugging
- pdb
---
Simply put

    import pdb; pdb.set_trace()

into a file named <code>debug.py</code> somewhere in your path. Then anywhere in your django app you just put
    
    import debug

and when you run that webpage it will seem to take a really long time. Just switch to the console and you will have a python debugger open. I usually just type normal python commands <code>print variable</code>, <code>dir(object)</code> but it also support commands like gdb. <code>c</code> for continue running, <code>n</code> for next line, etc...

Thanks to <a href="http://simonwillison.net/2008/May/22/debugging/">debugging django</a> for this tip.
