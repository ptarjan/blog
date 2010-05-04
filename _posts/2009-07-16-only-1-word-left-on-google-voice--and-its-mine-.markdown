--- 
permalink: /2009/07/only-1-word-left-on-google-voice-and.html
layout: post
title: Only 1 word left on google voice, and its mine!
tags: 
- phone number
- memorizing
- google voice
- phone
- google
- physics
- geek
image: http://www.iconspedia.com/uploads/16323851941876579956.png
---
I recently got an invitation to <a href="https://www.google.com/voice/">google voice</a> and have been trying to come up with a good number. I tried all the first 10 digits of <a href="http://www.ebyte.it/library/educards/constants/ConstantsOfPhysicsAndMath.html">physics constants</a> and every single 10 letter word in the ubuntu /usr/share/dict/words. Out of all of that, there was <b>ONLY 1</b> that was available.   

So I give you my new phone number (which is very easy to memorize, hehe) :  

    (MEM) ORI-ZING 
    (636) 674-9464

The 2 other leading candidates were :  

(209) 782-7526 (209) PTA-RJAN  

(707) 728-5468 (707) PAU-LIN8 (thanks <a href="http://twitter.com/ultramegaman/status/2678728642">ultramegaman</a>)  

Is it too much to ask for the number <b>(314) 159-2653</b>, <b>(299) 792-4580</b>, or <b>(137) 035-9990</b>? What is a geek to do...  

Here is the source of my script: 

{% highlight python %}
# This script will search google voice to see if there are any numbers
# available that spell a 10 letter word 
#
# It can easily be customized for 9 letters, or to use your own dictionary, etc.
#
# Author: Paul Tarjan <http://paulisageek.com>
#
# Make sure you put your own cookie here. Search the web if you don't know how to find it.
cookie = "DQAAA<rest of cookie>"

import urllib2
import re

def check(c) :
    global cookie
    r = urllib2.Request("https://www.google.com/voice/setup/search/?q=" + c, headers={"Cookie" : "gv=" + cookie})
    response = urllib2.urlopen(r)
    data = response.read()
    if '"Sign in"' in data:
        print "Bad cookie (probably)"
        return False
    if data.find('"num_matches":"0"') != -1 :
        return False
    return True

def dict(f="/usr/share/dict/words") :
    for word in file(f).read().split() :
        if len(word) == 10 and re.match("^[a-zA-Z0-9]+$", word) :
            if check(word) :
                print word

if "<rest of cookie>" in cookie:
    print "Please look up your google cookie and put it at the top of this file before running"
else:
    dict()
{% endhighlight %}

If it can help anyone, here is the list of the first 10 digits of all of the <a href="http://www.ebyte.it/library/educards/constants/ConstantsOfPhysicsAndMath.html">physics constants</a> on that site which are known to 10 digits or greater :   

    2997924580
    1054571628
    1256637061
    8854187817
    3767303134
    1602176487
    2417989454
    7297352537
    1370359996
    2067833667
    7748091700
    1290640377
    2581280755
    1758820150
    2426310217
    2817940289
    0665245855
    3636947519
    2002319304
    6582106848
    6582275971
    2802495364
    1097373156
    5291772085
    1660538782
    3990312682
    0119626564
    5485799094
    1602176487
    1660538782
    1672621637
    1321409844
    1410606662
    5585694713
    1674927211
    1319590895
    2002331841
    0433073465
    0857438230
    1074553298
    3243410198
