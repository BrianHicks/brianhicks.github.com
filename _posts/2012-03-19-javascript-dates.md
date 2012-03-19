---
layout: post
title: "javascript dates"
category: development
tags: [javascript]
---
{% include JB/setup %}
I've just spent half an hour wrestling with this, and for the benefit of
those to come...

{% highlight javascript %}
    d = new Date(2011, 12, 08)
{% endhighlight %}

Will produce a new datetime object, right? No biggie, if you look inspect it,
it displays like this:

{% highlight javascript %}
    "Thu Dec 08 2011 11:33:05 GMT-0600 (CST)"
{% endhighlight %}

But lo, the beast lurks. calling `getFullYear` and `getDate` work fine,
and return `2011` and `8`, respectively. But `getMonth` is a bit
different. See, the `Date` object thinks of January as month 0, February
as month 1, etc. So converting from one date to another (to get the
first of the month at midnight, for example) would be done like this in
Python:

{% highlight python %}
   >>> d = datetime.now()
   >>> month = datetime(d.year, d.month, 1)
{% endhighlight %}

But has to be done like this in Javascript:

{% highlight javascript %}
   d = new Date()
   month = new Date(d.getYear(), d.getMonth() - 1, 1)
{% endhighlight %}

Yes, I know that methods like `setDate` exist, but constructing a new
object with only what I need seems more efficient.

By the way, here's the way that [MongoDB](http://www.mongodb.org/) deals
with this in their `ISODate`:

{% highlight javascript %}
    var year = parseInt(res[1], 10) || 1970);
    var month = (parseInt(res[1], 10) || 1) - 1;
    var date = parseInt(res[3], 10) || 0;
{% endhighlight %}
