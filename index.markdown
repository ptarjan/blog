---
layout: root
title: Paul Tarjan's Blog
---
[<img src="http://paultarjan.com/paul.jpg" height="64" width="64" alt="Paul Tarjan" id="paul" />](http://paultarjan.com)

I was the Tech Lead for Yahoo! [SearchMonkey](http://developer.yahoo.com/searchmonkey/).
Now I'm a [juggling unicylcing](http://www.youtube.com/watch?v=vhvybkPa15c) web [hacker](http://paulisageek.com/ppp) @ Facebook. 
<br/>
[blog@paulisageek.com](mailto:blog@paulisageek.com)
my other <a href="http://paultarjan.com" rel="me">Internet Things</a>.

<div style="clear:both"></div>

{% for post in site.posts limit:1 %}
## [{{ post.title }}]({{ post.url }})
  {{ post.content }}
  *Posted on {{ post.date | date_to_long_string }}* by [Paul Tarjan](http://paultarjan.com)
{% endfor %}

## Archive

{% include archive.html %}
