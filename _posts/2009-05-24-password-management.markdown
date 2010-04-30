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

So, I've decided to generate a new random password per website and put all my usernames and passwords into an encrypted file on my hard drive. My process was 

{% highlight sh %}
# gpg passwords.gpg
# vim passwords
# gpg -c passwords
# rm passwords
{% endhighlight %}

This works fine, but sometimes I forget the last 2 steps and have a fully decrypted file sitting there... yeah... and the gpg -c would ask for my password 2 times in addition to the first gpg, so I end up typing it 3 times in total.

Enter <a href="http://github.com/ptarjan/gpg-encrypt/tree/master">gpg-encrypt</a>. It's just a simple shell script that reads in an encrypted file, edits it, then saves it back in an encrypted format.

Every time I have to register for a new website I: 
* Get a <a href="http://goodpassword.com/">good random password</a>
* Run ./gpg-encrypt
* Add the new information. I keep my file in <a href="http://www.yaml.org/">YAML</a> format incase I want to read it with a program later. Example:
{% highlight yaml %}
delicious.com : {
    username : ptarjan,
    password : WqgyzN9bJ6Pm
}
{% endhighlight %}
* Leave the editor and it goes back to being encrypted.

If I have to log in, I just do the same steps as above, but don't add anything. I can search using my editor for the domain of the site I'm looking for.

I backup my passwords.gpg file every time I add a new password, to another computer incase my linux box dies.

So, I hope this new password management works better for me than the last system. Anyone have any better solutions to this painful problem? And don't say <a href="http://ptarjan.myopenid.com">openid</a>, until 80% of the sites I visit support it :)

{% highlight sh %}
#!/bin/sh
filename="passwords.gpg"
if [ $EDITOR ]
then
    editor=$EDITOR
elif [ -f /usr/bin/editor ]
then
    editor=/usr/bin/editor
else
    editor=vi
fi

if [ $# = 0 ] 
then
    echo "No filename specified. Using default $filename"
elif [ $# > 1 ]
then
    echo "$0 [filename.gpg]"
    exit 2
fi

if [ -f `which shred` ]
then
    rm=shred
else
    rm=rm
fi

tmp=`mktemp` || exit 1

# don't show typing
stty -echo
read -p "Password: " passw; echo
stty echo

if [ ! -f $filename ]
then 
    echo "$filename doesn't exist. Starting from empty file."
elif [ ! -w $filename ]
then
    echo "$filename isn't writable."
    exit 1
else
    # decrypt into the tmp file
    echo "$passw" | gpg -q -d --passphrase-fd 0 $filename > $tmp
    if [ $? != 0 ]; then
        # if gpg didn't work, exit
        $rm $tmp
        exit $?;
    fi
fi

$editor $tmp
echo "$passw" | gpg -q -c --passphrase-fd 0 --output $filename $tmp
$rm $tmp
if [ $? != 0 ]; then
    # if gpg didn't work, exit
    exit $?;
fi
{% endhighlight %}
