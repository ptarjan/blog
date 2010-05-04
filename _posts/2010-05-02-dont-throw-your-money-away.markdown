---
permalink: /2010/05/02/dont-throw-your-money-away.html
layout: post
title: Don't throw your money away
tags: 
- amazon
- birthday
---
If you are ever buying something from Amazon, I can get 4% of your whole purchase as a 'referral fee'. If you let me know what you bought and your paypal, I'm more than happy to send you the money, or I'll buy you a drink in your honour.

If you just start your shopping with this link:

[Paul's amazon.com link](http://www.amazon.com/gp/redirect.html?ie=UTF8&location=http%3A%2F%2Fwww.amazon.com%2F&tag=paultarjan-20&linkCode=ur2&camp=1789&creative=390957)

I get the referral as long as you buy your item before you close your web browser (once you click that link).

If you don't want to find your item again, you can just put a product url here, and I have a handy form for adding in my referral code. Or if you want, you can just add it yourself:

    &tag=paultarjan-20

<script src="http://code.jquery.com/jquery-1.4.2.min.js"></script>

Amazon Product URL: 
<form id="convert">
<input name="amazon" id="amazon"/> 
<input type="submit" value="Add Paul's Code" />
<span id="amazon-link">paul's link appears here</span>
</form>

<script type="text/javascript">
//<![CDATA[
$("#convert").submit(function() {
  var url = $("#amazon").val();
  if (url.indexOf('?') == -1) {
    url += '?';
  } else {
    url += '&';
  }
  url += 'tag=paultarjan-20';
  var link = $('<a/>').attr('href', url).text(url);
  $('#amazon-link').text('').append(link);
  return false;
});
//]]>
</script>
