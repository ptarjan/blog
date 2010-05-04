---
permalink: /2010/04/30/blogging-with-jekyll.html
layout: post
title: Blogging With Jekyll
tags: 
- jekyll
- blog
image: /images/jekyll.png
---
As you may, or may not have noticed, I haven't been blogging much lately. I think this is due in part to how I was trying to use blogger. I was inserting my own html into the text box while blogging, and it was just a real pain to build a blog post. I had lots of control, but it was too much of a pain (and I'm lazy, so it didn't happen often).

I've also been really admiring clean and simple blog templates whenever I see them, and switching to that in blogger would require me to backport little things I would do in each post. 

So, I bit the bullet. I converted all my posts to [Markdown](http://daringfireball.net/projects/markdown/syntax). I originally planned on doing a `Markdown -> HTML` conversion and posting that to blogger, but then I realized that I could just use [jekyll](http://jekyllrb.com/) to build the whole thing. I lose a lot of the plugins in blogger (that I wasn't using much anyways) but I gain a lot of simplicity. And now I can write my blog posts in vim and host them as straight .html files! And their [source](http://github.com/ptarjan/ptarjan.github.com) is available! And... and... boy am I excited!

I exported my existing blog (Settings -> Basic -> Export Blog) to an .xml file. I then imported this file using [tannerburson](http://github.com/tannerburson/jekyll/blob/master/lib/jekyll/converters/blogger.rb)'s converter. I lost the command out of my history, but maybe a ruby enthusiast can let me know. Something like: 

{% highlight ruby %}
$ ruby ...stuff... "Jekyll::Blogger.process('feed.xml')"
{% endhighlight %}

It made me a [\_posts](http://github.com/ptarjan/ptarjan.github.com/tree/master/_posts/) directory. I then hand tuned each file to be in markdown instead of html and voila, you now have my new blog. I made jekyl match the permalink structure of my old blog, so no links should break. Let me know if anything goes wrong.

Hopefully I will post more with this new setup. If anyone have any subject requests let me know, and general comments are always welcome (like the format, hate the format, the RSS is broken, etc).

P.S. I wrote this whole post in markdown using vim, and it was **MUCH** nicer than doing it in blogger's textarea.
