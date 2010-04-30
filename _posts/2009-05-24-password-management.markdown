--- 
permalink: /2009/05/password-management.html
layout: post
title: Password Management
tags: 
- password
- linux
- geek
---
For the past 10 years I've been having a headache managing passwords for websites. I had about 7 levels of passwords and I could never decide which one to use on a website. And even once I decided, I would usually type them all trying to log in. If they logged my password attempts now they can go edit my Facebook profile, watch my Hulu shows, and buy stuff with my PayPal account (true story).

<p>
So, I've decided to generate a new random password per website and put all my usernames and passwords into an encrypted file on my hard drive. My process was 
<pre><code># gpg passwords.gpg
# vim passwords
# gpg -c passwords
# rm passwords
</code></pre>
<p>
This works fine, but sometimes I forget the last 2 steps and have a fully decrypted file sitting there... yeah... and the gpg -c would ask for my password 2 times in addition to the first gpg, so I end up typing it 3 times in total.

<p>
Enter <a href="http://github.com/ptarjan/gpg-encrypt/tree/master">gpg-encrypt</a>. It's just a simple shell script that reads in an encrypted file, edits it, then saves it back in an encrypted format.

<p>
Every time I have to register for a new website I: <ol><li>Get a <a href="http://goodpassword.com/">good random password</a></li><li>Run ./gpg-encrypt</li><li>Add the new information. I keep my file in <a href="http://www.yaml.org/">YAML</a> format incase I want to read it with a program later. Example:
<pre>
delicious.com : {
    username : ptarjan,
    password : WqgyzN9bJ6Pm
}
</pre>
</li><li>Leave the editor and it goes back to being encrypted.</li></ol>

<p>
If I have to log in, I just do the same steps as above, but don't add anything. I can search using my editor for the domain of the site I'm looking for.

<p>
I backup my passwords.gpg file every time I add a new password, to another computer incase my linux box dies.

<p>
So, I hope this new password management works better for me than the last system. Anyone have any better solutions to this painful problem? And don't say <a href="http://ptarjan.myopenid.com">openid</a>, until 80% of the sites I visit support it :)
<script src="http://gist.github.com/117322.js"></script>
