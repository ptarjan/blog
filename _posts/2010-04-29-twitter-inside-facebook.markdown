---
layout: post
title: Twitter inside Facebook
tags: 
- facebook
- twitter
- announcement
- hack
---
[<img src="http://t2fb.paulisageek.com/images/t2fb.png" class="right">](http://t2fb.paulisageek.com)

With the launch of Facebook's like button, I hoped I could do something that I've wanted to do for a while. Create a mirror page of each twitter page inside of facebook. That way, I can just "like" that page, and now I don't have to have to check facebook AND twitter.

And voila! It actually worked! Try it for yourself.

[Twitter 2 Facebook](http://t2fb.paulisageek.com)

You can either "like" individual people (like [mine](http://t2fb.paulisageek.com/ptarjan)) or choose from [all your existing followees](http://t2fb.paulisageek.com/followers). Once you click "like" then all twitter posts by that person will show up in your facebook feed. You can unlike it any time (from your profile, or the original page).

If this takes off, then I'll buy a better domain for it. Any suggestions for the name (that are avilable)?

--

For the geeks: this uses PHP to proxy the twitter pages, and [node.js](http://nodejs.org) for the backend. 
Each proxy page has [open graph](http://opengraphprotocol.org) data embed in it, so that when a person "likes" it, they give my [facebook app](http://www.facebook.com/apps/application.php?id=117020064991268) permission to post to their feed. 
When you like a page, you ping my backend telling it to start listening to that user's tweets.
My backend then, connects to the twitter streaming API and sets the follow list to all the people who have been "liked".
When a tweet comes in, it goes right back out to the corresponding facebook page using the `stream.publish` API.

As a byproduct, I built a [node.js cache](http://github.com/ptarjan/node-cache) that you might find useful. When a cache key expires it actually purges it, so you don't end up with tons of memory usage, nor need garbage collection.
