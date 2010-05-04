--- 
permalink: /2009/06/equivalent-openids.html
layout: post
title: Equivalent OpenIDs
tags: 
- openid
- yql
- equivilent openids
- internet
- geek
image: http://openid.net/images/logo/openid-icon-100x100.png
---
I've been having a big dilemma whenever I use an openid. Which do I pick from the 8 that could be me? Talking to <a href="http://josephsmarr.com/">Joseph Smarr</a> at the <a href="https://labs.mozilla.com/2009/06/mozilla-labs-meetup-thursday-625/">Mozilla labs meetup</a> we stumbled upon a solution. <a href="http://microformats.org/wiki/rel-me">rel-me</a>.

I should register on any site with an openid that supports at least 1 rel-me link. Most sites where you can set your "homepage" will add the attribute <b>rel="me"</b> on the link. That basically says that "I am also over there". If you can only link to one homepage, just make sure that from that homepage you can link out to other things you own on the internet. If you can put multiple <b>rel="me"</b> links, then just list everything you own. I link to my <a href="http://friendfeed.com/ptarjan">friendfeed.com/ptarjan</a> which has <b>rel="me"</b> links to all my other "stuff".

Then when I log into any openid provider they should check the social graph to see if the openid I just used is equivalent to any other one. Google made a <a href="http://code.google.com/apis/socialgraph/">simple API</a> to query the graph. This has one problem in that they crawl the graph recursivly on outbound links. Meaning they are trying to start at a webpage and find other things from there. That doesn't stop me from saying that <b>twitter.com/cnn</b> is me. For identity you want to crawl the graph backwards. Similar as to how PageRank only trusts inbound links.

I made a <a href="http://github.com/ptarjan/yql-tables/blob/b46262062ea2ae715efe2e0d95b6cb2967c0f6a4/socialgraph/socialgraph.trustsme.xml">YQL execute</a> file (<a href="http://paulisageek.com/yql-tables/socialgraph/socialgraph.trustsme.xml">raw code</a>) that will compute which URIs trust a given URI.

For example, if I log in with 

    http://paulisageek.com

then the website that I logged in to should make the <a href="http://query.yahooapis.com/v1/public/yql?q=USE%20'http%3A%2F%2Fpaulisageek.com%2Fyql-tables%2Fsocialgraph%2Fsocialgraph.trustsme.xml'%3B%20SELECT%20*%20FROM%20socialgraph.trustsme%20WHERE%20q%3D'http%3A%2F%2Fpaulisageek.com'&format=xml&env=http%3A%2F%2Fdatatables.org%2Falltables.env">YQL call</a>

    USE 'http://paulisageek.com/yql-tables/socialgraph/socialgraph.trustsme.xml'; SELECT * FROM socialgraph.trustsme WHERE q='http://paulisageek.com'

which returns something like

{% highlight xml %}
<query>
    <results>
        <result>
            <trustsme>http://www.paulisageek.com/</trustsme>
            <trustsme>http://www.linkedin.com/pub/dir/paul/tarjan</trustsme>
            <trustsme>http://stackoverflow.com/users/90025/ptarjan</trustsme>
            <trustsme>http://www.mybloglog.com/buzz/members/ptarjan/</trustsme>
            <trustsme>http://digg.com/users/paralax/</trustsme>
            <trustsme>http://www.google.com/profiles/114701835473476527933</trustsme>
            <trustsme>http://www.flickr.com/photos/ptarjan/</trustsme>
            <trustsme>http://www.linkedin.com/in/paultarjan</trustsme>
            <trustsme>http://twitter.com/ptarjan</trustsme>
            <trustsme>http://github.com/ptarjan</trustsme>
            <trustsme>http://www.hulu.com/profiles/ptarjan</trustsme>
            <trustsme>http://stackoverflow.com/users/90025/paul-tarjan</trustsme>
            <trustsme>http://friendfeed.com/ptarjan</trustsme>
            <trustsme>http://www.google.com/profiles/ptarjan</trustsme>
            <trustsme>http://www.flickr.com/photos/78332988@N00/</trustsme>
            <trustsme>sgn://twitter.com/?pk=14757201</trustsme>
        </result>
    </results>
</query>
{% endhighlight %}

and then walk down that list starting at the top, looking at all their user accounts to see if any matches. The first match is the account they should be logged into.

Every one of these trust relationships is explicitly put there by the user by a link with <b>rel="me"</b> so it can be trusted just as much as the original openid provider. For example, if there is a link on <code>http://twitter.com/ptarjan</code> with <b>rel="me"</b> to <code>http://paulisageek.com</code>, my twitter account is giving permission to paulisageek to modify any account it owns. If my twitter account were to be hacked to point to another place with <b>rel="me"</b>, that is equivalent to the openid login for that URI to be hacked as well. All sites that I am aware of use the same credentials to edit the <b>rel="me"</b> link as for the openid identity login. With this assumption, the trust relationship is valid.

In conclusion, every site that is using openid, should check inbound <b>rel="me"</b> links to the openid URI. Using the <a href="http://socialgraph.apis.google.com/">socialgraph API</a> I created a helper <a href="http://query.yahooapis.com/v1/public/yql?q=USE%20'http%3A%2F%2Fpaulisageek.com%2Fyql-tables%2Fsocialgraph%2Fsocialgraph.trustsme.xml'%3B%20SELECT%20*%20FROM%20socialgraph.trustsme%20WHERE%20q%3D'http%3A%2F%2Fpaulisageek.com'&format=xml&env=http%3A%2F%2Fdatatables.org%2Falltables.env">REST API</a> that can be used to take any URI and find other URIs that trust it.
