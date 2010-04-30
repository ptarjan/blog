--- 
permalink: /2009/10/rock-band-group-algorithm.html
layout: post
title: Rock Band Group Algorithm
tags: 
- games
- rock band
- video games
---
<img src="http://upload.wikimedia.org/wikipedia/en/e/e0/Rock_band_cover.jpg" class="right">

I often play [Rock Band](http://en.wikipedia.org/wiki/Rock_Band_%28video_game%29) with my friends, but we have a tough time deciding who will play what part and for how long. Here is what we've come up with as requirements

* Everyone must play every instrument an equal amount of time - To avoid hogging
* Every time a person is on an instrument, they must play with a different combination of people - To play on other people's strengths and avoid other's weaknesses
* Sitting out many songs in a row is minimized

Does anyone else have other constraints they play with?

Given these requirements, here is what we do:

1. Lay the 4 instruments out and randomly put 4 people on them, and intersperse the remaining people in the gaps between instruments
1. Cycle everyone through every instrument and every gap (clockwise), until we arrive back at the initial state
1. Shuffle everyone like this:
 1. Group the people into 2 groups. Those on instruments (size `4`) and those not (size `n-4`)
 1. Pick 4 people from the non-instruments and randomly put them on instruments
 1. If you have less than 4 people on non-instruments, select random people to stay on instruments, but change their instruments randomly
 1. Randomly permute the remaining people into the open spots
1. Play another round and then re-cycle

## Notes

* Designate one guitar as the *Guitar*, and one as the *Bass*. We choose the one with the solo fretboard as the Guitar.
* The singer picks the song since it is the hardest to do if you don't know the song.
* If you fail a song, if you are &lt;50% complete, you play again, if you are &gt;50% you move to the next instruments. If you fail again, you add your %s together.
* We don't replay the same song that we already played unless we REALLY need to.

This can work for other games, like Guitar Hero or even non-music games. Just change the number 4 to however many slots you have and run it.

I'm interested in how other people do this. I like fairness, but I also like not having to have a complicated system that requires white boards, a master planner, and a dictator.

And what kind of geek would I be if I didn't have some code to solve this problem

{% highlight bash %}
$ python rockband.py Paul Michelle Martin Melanie Surbhi Ziga Emily
Drums:  Martin
Vocals: Ziga
 Gap:   Melanie
Guitar: Surbhi
 Gap:   Paul
Bass:   Michelle
 Gap:   Emily
Press &lt;Enter&gt; once you finished a round: 

Drums:  Paul
Vocals: Ziga
 Gap:   Surbhi
Guitar: Emily
 Gap:   Michelle
Bass:   Melanie
 Gap:   Martin
Press &lt;Enter&gt; once you finished a round: 

Drums:  Surbhi
Vocals: Martin
 Gap:   Paul
Guitar: Michelle
 Gap:   Melanie
Bass:   Emily
 Gap:   Ziga
Press &lt;Enter&gt; once you finished a round: q
{% endhighlight %}

and in `rockband.py`

{% highlight python %}
import random
import sys

instruments = ["Drums", "Vocals", "Guitar", "Bass"]

people = sys.argv[1:]
if len(people) == 0:
    print "python rockband.py Name1 Name2 ..."
    sys.exit()
if len(people) < len(instruments):
    print "If there is less than %d people, just pick some instruments, "+\
      "rotate, and then shuffle. You don't need me for that"\
      % len(instruments)
    sys.exit()

random.shuffle(people)
num = len(people)

places = [' Gap']*num
instruments_ids = [0, int(num*0.25), int(num*0.5), int(num*0.75)]
for i, ins in zip(instruments_ids, instruments):
    places[i] = ins

while True :
    for l,n in zip(places, people):
        print "%s:\t%s" % (l, n)

    if raw_input("Press <Enter> once you finished a round: ") == "q" :
        break

    print ""
    playing = [people[x] for x in instruments_ids]
    not_playing = list(set(people) - set(playing))

    if len(not_playing) < len(instruments) :
        new_playing = not_playing +\
          random.sample(playing, len(instruments) - len(not_playing))
    else :
        new_playing = random.sample(not_playing, len(instruments))

    new_not_playing = list(set(people) - set(new_playing))
    random.shuffle(new_playing)
    random.shuffle(new_not_playing)

    people = [None]*num
    for i, p in zip(instruments_ids, new_playing) :
        people[i] = p

    count = 0
    for i in xrange(len(people)) :
        if not people[i] :
            people[i] = new_not_playing[count]
            count += 1
{% endhighlight %}

This code doesn't work very well with 9 people as they will always be playing with the same group, but at least their instruments will change. All other sizes should work well.
