---
layout: post
title: Debugging URLs with the Facebook URL Linter
tags:
- facebook
---
*Republished from [Facebook Developer's Blog](http://developers.facebook.com/blog/post/390)*

A primary design goal of the [Open Graph protocol][] -- which
enables any Web page to become a rich object in the social graph --
has been to make it simple for developers to integrate it into
their Web pages. But, as with any coding, syntax errors can and do
occur. To help you debug your URLs, we've released the
[Facebook URL Linter][].

You can use the Facebook URL Linter with many types of URLs, in
addition to Open Graph protocol pages. Try the linter on our
[homegrown examples][] or on [some][] [pages][] [in][] [the][]
[wild][].

![image][]

At this time, the linter returns warnings for any issues it
encounters. In the near future, the linter will start returning
errors. These errors will cause the [Like button][] to stop working
on your page.

We also plan to add Open Graph protocol type metadata suggestions,
and a lot of helpful messaging. If you have any feedback, we'd love
to hear it on the [Developer Forum][]. Make sure to put [linter][]
somewhere in the post, to help us find it.

This week we've also added Open Graph protocol markup to every
public Page on Facebook. This makes it easy for anyone to know that
[Starbucks][] is a company, the [White House][] is part of the
government, and [Weird Al][] is my favorite musician.

[Lint][Facebook URL Linter] away!

*Paul is a lint-free, [white and nerdy][] hacker on the Platform team.*

**Note:** In case you were wondering, the Facebook URL Linter's
name hails from [Douglas Crockford][]'s [JS Lint][].

  [Open Graph protocol]: http://developers.facebook.com/docs/opengraph
  [Facebook URL Linter]: http://developers.facebook.com/tools/lint/
  [homegrown examples]: http://developers.facebook.com/tools/lint/examples/
  [some]: http://developers.facebook.com/tools/lint/?url=opengraphprotocol.org
  [pages]: http://developers.facebook.com/tools/lint/?url=http://www.imdb.com/title/tt0117500/
  [in]: http://developers.facebook.com/tools/lint/?url=developers.facebook.com
  [the]: http://developers.facebook.com/tools/lint/?url=http://www.rottentomatoes.com/m/matrix/
  [wild]: http://developers.facebook.com/tools/lint/?url=blog.paulisageek.com
  [image]: http://sphotos.ak.fbcdn.net/hphotos-ak-snc3/hs632.snc3/31689_410953598552_19292868552_4354726_6115323_n.jpg
  [Like button]: http://developers.facebook.com/docs/reference/plugins/like
  [Developer Forum]: http://forum.developers.facebook.com/viewforum.php?id=51
  [linter]: http://forum.developers.facebook.com/search.php?action=search&keywords=linter
  [Starbucks]: http://www.facebook.com/Starbucks
  [White House]: http://www.facebook.com/WhiteHouse
  [Weird Al]: http://www.facebook.com/weirdal
  [white and nerdy]: http://www.youtube.com/watch?v=vhvybkPa15c
  [Douglas Crockford]: http://www.crockford.com/
  [JS Lint]: http://www.jslint.com/
