---
layout: post
title: "dict syntax"
category: development
tags: [python]
---
{% include JB/setup %}
I just found out something neat about Python's `dict` syntax. First of
all, of course this works:

{% highlight python %}
    >>> d = dict(a=1, b=2, c=3)
{% endhighlight %}

But you can also stick dictionaries in there as the first argument. Go
ahead, try it:

{% highlight python %}
    >>> d = {'a': 1, 'b': 2}
    >>> d2 = dict(d, a=2, b=3)
    >>> d2
    {'a': 2, 'b': 3}
{% endhighlight %}

It's as if you called `update` on the dictionary. Neato, eh? It's
especially useful in [ming migrations][ming-migrations].

[ming-migrations]: http://merciless.sourceforge.net/tour.html#specifying-a-migration "Specifying a migration"
