--- 
permalink: /2009/07/openid-avatar.html
layout: post
title: OpenID Avatar
tags: 
- openid
- openidavatar
- gravatar
- announcement
image: http://paulisageek.com/openidavatar/avatar/9884a6211d8e83a7770550708f5785cf?email_md5=b3bb70a4bace7f9bd49f48b149ab95f9&size=200
---
[gravatar](http://gravatar.com) does a wonderful job with email avatars, but they have failed to support OpneIDs. I built a simple interface for associating your OpenID with an email, which is then proxied to gravatar.   

So I give you <a href="http://paulisageek.com/openidavatar/">OpenID Avatar</a>.  

Simply change your gravatar urls to use <b>http://paulisageek.com/openidavatar/avatar/</b> instead of <b>http://www.gravatar.com/avatar/</b> Then you can use md5s of openids in addition to emails. If you want to use them both, just set the <b>email_md5</b> param as well. See the img in this post for an example, or see the <a href="http://paulisageek.com/openidavatar/site/implement">docs</a>.  

To setup your openid to email link, simply <a href="http://paulisageek.com/openidavatar/site/login/">login</a> and pick which email to associate with. Done.  

Suggestions are always welcome.
