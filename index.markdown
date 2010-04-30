---
layout: root
title: Paul Tarjan's Blog
---
[<img src="http://paultarjan.com/paul.jpg" height="64" alt="Paul Tarjan" id="paul" />](http://paultarjan.com)

I was the Tech Lead for Yahoo! [SearchMonkey](http://developer.yahoo.com/searchmonkey/).
Now I'm a [juggling unicylcing](http://www.youtube.com/watch?v=vhvybkPa15c) web [hacker](http://paulisageek.com/ppp) @ Facebook. 
<br/>
[blog@paulisageek.com](mailto:blog@paulisageek.com)
my other <a href="http://paultarjan.com" rel="me">Internet Things</a>.

<div style="clear:both"></div>

{% for post in site.posts limit:5 %}
## [{{ post.title }}]({{ post.url }})
  {{ post.content }}
  <em>Posted on {{ post.date | date_to_long_string }}</em> by [Paul Tarjan](http://paultarjan.com)
{% endfor %}

## Archive

<ul id="archive">
{% for post in site.posts %}
  <li>
    <abbr>{{ post.date | date_to_string }}</abbr>
    <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>
