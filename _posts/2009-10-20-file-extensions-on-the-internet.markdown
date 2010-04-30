--- 
permalink: /2009/10/file-extensions-on-internet.html
layout: post
title: File Extensions on the Internet
tags: 
- data
- hack
---
I simply wanted to know *Which file extensions are used on the internet*?

So I wrote a little program ([webExtension.py]("http://paulisageek.com/webExtension/webExtension.py")) and a half million calls to Google later, we have some interesting data.

First, the raw data:

* Alphabetical : 
<a href="http://paulisageek.com/webExtension/1.txt">1</a>
<a href="http://paulisageek.com/webExtension/2.txt">2</a>
<a href="http://paulisageek.com/webExtension/3.txt">3</a>
<a href="http://paulisageek.com/webExtension/4.txt">4</a>
<a href="http://paulisageek.com/webExtension/all.txt">All</a>
<a href="http://paulisageek.com/webExtension/all_pruned.txt">All (Pruned)</a>
* Numerical :
<a href="http://paulisageek.com/webExtension/1_numsort.txt">1</a>
<a href="http://paulisageek.com/webExtension/2_numsort.txt">2</a>
<a href="http://paulisageek.com/webExtension/3_numsort.txt">3</a>
<a href="http://paulisageek.com/webExtension/4_numsort.txt">4</a>
<a href="http://paulisageek.com/webExtension/all_numsort.txt">All</a>
<a href="http://paulisageek.com/webExtension/all_numsort_pruned.txt">All (Pruned)</a>

<style>
td.num {
  text-align: right;
}
</style>

<table style="margin:auto; text-align:left">
<tr><td>
  <a href="http://www.google.com/search?q=ext%3Ahtml">html</a>
</td><td class="num">
  6 700 000 000
</td></tr><tr><td>
  <a href="http://www.google.com/search?q=ext%3Aphp">php</a>
</td><td class="num">
  5 980 000 000
</td></tr><tr><td>
  <a href="http://www.google.com/search?q=ext%3Ahtm">htm</a>
</td><td class="num">
	1 690 000 000
</td></tr><tr><td>
  <a href="http://www.google.com/search?q=ext%3Aasp">asp</a>
</td><td class="num">
  1 510 000 000
</td></tr><tr><td>
  <a href="http://www.google.com/search?q=ext%3Aaspx">aspx</a>
</td><td class="num">
  1 380 000 000
</td></tr><tr><td>
  <a href="http://www.google.com/search?q=ext%3Ajsp">jsp</a>
</td><td class="num">
  565 000 000
</td></tr><tr><td>
  <a href="http://www.google.com/search?q=ext%3Acfm">cfm</a>
</td><td class="num">
  385 000 000
</td></tr><tr><td>
  <a href="http://www.google.com/search?q=ext%3Apdf">pdf</a>
</td><td class="num">
  298 000 000
</td></tr><tr><td>
  <a href="http://www.google.com/search?q=ext%3Ado">do</a>
</td><td class="num">
  242 000 000
</td></tr><tr><td>
  <a href="http://www.google.com/search?q=ext%3Acgi">cgi</a>
</td><td class="num">
  199 000 000 
</td></tr>
</table>	

Some interesting facts I saw :

* There are <b>1305</b> unused 3 letter extensions out of the possible <b>17,576</b>. That is <b>92.5%</b> are already used for something. (There IS a lot of junk thought, so don't be TOO alarmed).
* There are a lot of common extensions that I have NO idea what they are for. <code>.e</code>? <code>.nhn</code>?
* 4x more pages are <b>html</b> instead of just <b>htm</b>.
* PHP is beating ASP by about 2x.
* Many servers serve HTML from image extensions, and jpg > png == gif > svg > jpeg > bmp > tiff
* Naming is mostly not biased by first letter. The empty part is 3 letter extensions starting with <b>y</b>. 
* ![alphabetic](http://1.bp.blogspot.com/_cqlm7VAZ-hU/St7BcCIw9zI/AAAAAAAAAHA/EEEj3Lhf3Sk/s400/alphabetic.png)
* Only the top 5,000 extensions have more than 1000 pages. 
* ![alphabetic](http://4.bp.blogspot.com/_cqlm7VAZ-hU/St7D5jwVFVI/AAAAAAAAAHI/n7Vd3VOjXK4/s400/numeric.png)

Some caveats

* This was done in October 2009, things might change. I'll rerun it if people leave comments.
* I only looked for extensions up to 4 letters. No numbers or funky symbols.
* I am assuming the counts on Google's search results are ACTUALLY correct.

If anyone makes any interesting observations with this data, please let me know and I'll post it here. Pretty graphs are welcome as well :)
