---
title: Temptation of Pypy
date: 2013-09-24
layout: default
---
So last week I attended [Strangeloop](https://thestrangeloop.com/) (which was
excellent, by the way, and you should go if you ever have the slightest
chance.) I had a couple conversations with people about performance and JIT
compilers and stuff like that, and right now I'm really tempted to try out
Pypy. The target project which I'm thinking about has the following properties:

 - Mostly Python (i.e. few C extensions)
 - Needs to be *fast*. (last week NewRelic measured it at 11.9ms response time)
 - Calls the same methods over and over with the same types.

BUT, it also has this going on:

 - The DB persistence is pymongo/hiredis (the only two C extensions here)
 - Those few methods are called with complex types (specifically, Django's
   request objects.) I've heard this can be a problem for JIT compilers, and if
   it is I don't know that we'll fully realize the speed gains.

So I'm torn, and that's why I'm putting it up here: can anyone with experience
running Pypy in production shed some light on these concerns, or am I going to
have to just try it and measure performance?
