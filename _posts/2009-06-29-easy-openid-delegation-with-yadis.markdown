--- 
permalink: /2009/06/easy-openid-delegation-with-yadis.html
layout: post
title: Easy OpenID Delegation with Yadis
tags: 
- openid
- xml
- delegation
- yadis
---
<img src="http://openid.net/images/logo/openid-icon-100x100.png" class="left" /> Lets say you have a site somewhere that you want to use as your openid. The easiest way to delegate OpenID is to put these in your `<head>`

    <link href='http://www.myopenid.com/server' rel='openid.server'/>
    <link href='http://ptarjan.myopenid.com/' rel='openid.delegate'/>

That requires that the URL you are putting them on returns HTML. For me, I have a <a href="http://en.wikipedia.org/wiki/HTTP_302">302</a> redirect from <a href="http://paulisageek.com">http://paulisageek.com</a> to <a href="http://blog.paulisageek.com">http://blog.paulisageek.com</a> so all of my enpoints are getting my identity as <a href="http://blog.paulisageek.com">http://blog.paulisageek.com</a>. Not what I wanted.

Enter : <a href="http://en.wikipedia.org/wiki/Yadis">Yadis</a>. I created a small Yadis file that says the same thing as those `link` elements. <a href="http://paulisageek.com/openid.xml">openid.xml</a>.

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<xrds:XRDS xmlns:xrds="xri://$xrds" xmlns="xri://$xrd*($v*2.0)" xmlns:openid="http://openid.net/xmlns/1.0">
<XRD>
    <Service priority="10">
        <Type>http://openid.net/signon/1.0</Type>
        <URI>http://www.myopenid.com/server</URI>
        <openid:Delegate>http://ptarjan.myopenid.com/</openid:Delegate>
    </Service>
    <Service priority="20">
        <Type>http://openid.net/signon/1.0</Type>
        <URI>http://draft.blogger.com/openid-server.g</URI>
        <openid:Delegate>http://paulisageek.blogspot.com/</openid:Delegate>
    </Service>
</XRD>
</xrds:XRDS>
{% endhighlight %}

And then redirect it if the <a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html">HTTP Accept</a> header is `application/xrds+xml`. This is my index.php on `paulisageek.com</code> :

{% highlight php %}
<?php
if (strpos($_SERVER['HTTP_ACCEPT'], "application/xrds+xml") !== FALSE) {
    header("Content-Type: application/xrds+xml");
    echo file_get_contents("openid.xml");
    die();
} else {
    header("Location: http://blog.paulisageek.com");
    die();
}
?>
{% endhighlight %}

And Voila, it work as an <a href="http://openidenabled.com/resources/openid-test/checkup/start?openid_url=http%3A%2F%2Fpaulisageek.com">openid endpoint</a>.

<b>Update:</b> You can also use <a href="http://httpd.apache.org/docs/2.0/mod/mod_rewrite.html">mod_rewrite</a> to get people to your openid.xml file : 

{% highlight apache %}
    RewriteCond %{HTTP_ACCEPT} application/xrds\+xml
    RewriteRule .* openid.xml [T=application/xrds+xml,L]
{% endhighlight %}

You can replace `.*` with the urls that you want to be allowed openids, but I intentionally have `.*` so that I can have unlimited openids for myself.
