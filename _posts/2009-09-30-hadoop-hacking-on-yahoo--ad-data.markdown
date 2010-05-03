--- 
permalink: /2009/09/hadoop-hacking-on-yahoo-ad-data.html
layout: post
title: Hadoop Hacking on Yahoo! Ad Data
tags: 
- cmu
- hacku
- hack
---
At the <a href="http://developer.yahoo.com/hacku/cmu.html">CMU Hackday</a> we're letting students play with an anonymized snapshot of our advertising data. (If you want access, email <a href="mailto:jamieloc [NOSPAM] yahoo-inc.com?subject=Can I have the Yahoo hadoop data, please&body=Can you send me the thing to sign please.">Jamie</a>, sign something, and we'll give you a key).

Basically, we have a cluster of EC2 machines running hadoop with the data loaded to play with. So, of course, I wanted to play. 

Here is the README about the data

    (1) "ydata-ysm-keyphrase-bid-imp-click-v1_0.gz" contains the following fields:

    0 day
    1 anonymized account_id
    2 rank
    3 anonymized keyphrase (expressed as list of anonymized keywords)
    4 avg bid
    5 impressions
    6 clicks

Snippet:

    1       08bade48-1081-488f-b459-6c75d75312ae    2       2affa525151b6c51 79021a2e2c836c1a 327e089362aac70c fca90e7f73f3c8ef af26d27737af376a    100.0     2.0     0.0
    29      08bade48-1081-488f-b459-6c75d75312ae    3       769ed4a87b5010f4 3d4b990abb0867c8 cd74a8342d25d090 ab9f74ae002e80ff af26d27737af376a    100.0     1.0     0.0
    29      08bade48-1081-488f-b459-6c75d75312ae    2       769ed4a87b5010f4 3d4b990abb0867c8 cd74a8342d25d090 ab9f74ae002e80ff af26d27737af376a    100.0     1.0     0.0
    11      08bade48-1081-488f-b459-6c75d75312ae    1       769ed4a87b5010f4 3d4b990abb0867c8 cd74a8342d25d090 ab9f74ae002e80ff af26d27737af376a    100.0     2.0     0.0

I like python, and <a href="http://hadoop.apache.org/common/docs/current/streaming.html">hadoop streaming</a> lets me use it for map reducing. You basically write two scripts, <code>map.py</code> and <code>reduce.py</code> which work on stdin, and stdout. Here is me making those files

{% highlight sh %}
mkdir money_made_rank
vim money_made_rank/map.py
<code it>
vim money_made_rank/reduce.py
<code it>
{% endhighlight %}

map.py:

{% highlight python %}
#!/usr/bin/python
import sys
import random

for line in sys.stdin :
 line = line.strip()
 cols = line.split('\t')
 if len(cols) != 7 :
  continue
 day, account, rank, keyprase, bid, impressions, clicks = cols
 clicks = float(clicks)
 if clicks == 0 :
  continue
 bid = float(bid)
 money = clicks * bid
 print "%s\t%f" % (rank, money)
{% endhighlight %}

reduce.py:

{% highlight python %}
#!/usr/bin/python
import sys
from operator import itemgetter

result = {}

for line in sys.stdin :
 line = line.strip()
 key, money = line.split('\t', 1)
 try :
  money = float(money)
  result[key] = result.get(key, 0) + money
 except :
  continue
 
sorted_result = sorted(result.items(), key=itemgetter(0))
for key, money in sorted_result :
 print "%s\t%f" % (key, money)
{% endhighlight %}

Then you should test your stuff locally. For that, we left the .gz file and I just ran :

{% highlight sh %}
zcat /mnt/data/ydata-ysm-keyphrase-bid-imp-click-v1_0.gz | head -n 1000 | money_made_rank/map.py | sort | money_made_rank/reduce.py
{% endhighlight %}

And if it spits out

    1       3540.000000
    2       14604.489767
    3       13516.602689
    4       2668.682927
    5       2250.000000
    6       540.000000
    7       540.000000

then you're doing it right. 

If you want to run on one machine then just take out the <code>head -n 1000</code>. That should take about 20 minutes to chew through all the data.

## Lets move to hadoop

Once it works in the piping mode, then it is very simple to just do it on the cluster. Don't change any files, just type :

{% highlight sh %}
hadoop jar /usr/lib/hadoop/contrib/streaming/hadoop-0.18.3-14.cloudera.CH0_3-streaming.jar 
  -input /data/ydata/* 
  -output money_made_rank 
  -mapper money_made_rank/map.py 
  -reducer money_made_rank/reduce.py 
  -file money_made_rank/*
{% endhighlight %}

This will print out a whole bunch of stuff and at the end you should have a `money_made_rank` directory. Just print it and bask in the glory:

{% highlight sh %}
hadoop fs -cat 'money_made_rank/part-*' | sort -n
{% endhighlight %}

and it should print out :

    1 14743915410.559452
    2 5671857020.978109
    3 3580521727.805751
    4 1770068342.652887
    5 1141008200.372228
    6 531839794.947136
    7 360624250.037246
    8 266172741.734491
    9 213458413.893067
    10 189563018.302472
    ...

And then you can put it in a spreadsheet and make a pretty chart. Did you know half of our money comes from the #1 Search Ad?

<iframe src="http://spreadsheets.google.com/pub?key=tK-7SP4HSyN4F9Z91MVyR_Q&gid=1" style="height:500px; width: 100%"></iframe>
