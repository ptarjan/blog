--- 
permalink: /2009/06/incomplete-format.html
layout: post
title: Incomplete Format
tags: 
- linux
- python
- code
---
Anyone who is getting <b>ValueError: incomplete format</b> exceptions when doing a string format in python should understand that the part inside the () is just an array lookup. You still need a format type after it.

<pre><code>I have %(count) %(adj) %(noun)</code></pre>

doesn't work since you didn't say they were integers and strings. You need to do

<pre><code>I have %(count)i %(adj)s %(noun)s</code></pre>

which is the same as 

<pre><code>I have %i %s %s</code></pre>

with position indexed values.
