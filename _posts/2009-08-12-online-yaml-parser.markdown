--- 
permalink: /2009/08/online-yaml-parser.html
layout: post
title: Online YAML parser
tags: 
- yaml
- json
- geek
- announcement
---
<a href="http://yaml-online-parser.appspot.com/"><img src="http://swik.net/swikIcons/img-240-96x96.jpg" class="left" /></a> 

So, today I needed to verify some <a href="http://yaml.org">YAML</a> was correct, and eyeball the <a href="http://json.org">JSON</a> output. I couldn't find a good tool online that did what I wanted, so I wrote my own in about an hour.  

I give you the <a href="http://yaml-online-parser.appspot.com/">Online YAML Parser</a>.   

It takes in YAML and outputs JSON using pyYAML. Simple, but useful. <a href="http://yaml-online-parser.appspot.com/?yaml=-%20Mark%20McGwire%0A-%20Sammy%20Sosa%0A-%20Ken%20Griffey%0A">Try</a> <a href="http://yaml-online-parser.appspot.com/?yaml=canonical%3A%201.23015e%2B3%0Aexponential%3A%2012.3015e%2B02%0Afixed%3A%201230.15%0Anegative%20infinity%3A%20-.inf%0Anot%20a%20number%3A%20.NaN%0A">some</a> <a href="http://yaml-online-parser.appspot.com/?yaml=null%3A%0Abooleans%3A%20[%20true%2C%20false%20]%0Astring%3A%20%27012345%27%0A">examples</a> from the <a href="http://www.yaml.org/spec/1.2/spec.html">1.2 spec</a>, or paste in your own, and let me know of any bugs.
