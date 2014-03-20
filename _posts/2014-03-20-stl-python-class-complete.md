---
layout: post
title: "STL Python: Class Complete"
category: development
tags: [python]
---
{% include JB/setup %}
[STL Python](http://meetup.com/stl-python) has just finished it's inaugural programming class: Intro to Programming with Python. With slightly more than a full class, I'd call it a success.

## Why offer a class in the first place?

As a whole, I think programming is an interesting career, and I've found enjoyment and employment there. But in a bigger picture, it's a *great* "secret weapon" in a non-tech field. Case in point, we had researchers from Washington University join the class because they needed to learn how to program in order to further their own research.

There is a bigger reason to teach programming: tech is monocultural. Diversity of thought and opinion will make stronger people that do more good in their communities. (And as an aside, maybe we can stop making products that *only* rich white guys will ever want and start doing some stuff that to the benefit of people outside the tech scene.) By teaching people outside our sphere how to program we're not only increasing their economic opportunity but our own chances of survival. There are a lot of thoughts and organizations working on this: [The Ada Initiative's FAQ](http://adainitiative.org/faq/#why-focus-on-women-in-open-technology-and-culture), [Ashe Dryden's Blog](http://www.ashedryden.com/), [Rails Girls](http://railsgirls.com/), and [this article on Color Lines](http://colorlines.com/archives/2013/10/where_are_people_of_color_in_nycs_silicon_alley.html) are a few good places to look if you're interested in learning more about tech's diversity problem.

It would also show lack of care on my part to not mention that Tony Becker (my co-teacher for this class) has also published [some thoughts on this](http://fortpedro.com/2014/01/why-learn-to-code/).

## Hitting the ground running

Tony approached me about co-teaching a introductory programming class early in 2014. I've wanted a class for St. Louis for a long time, but never had the gumption to do alone. We started planning out our curriculum right away. We chose [*How to Think Like a Computer Scientist* by Allen B. Downey](http://www.greenteapress.com/thinkpython/) to teach the course with since it is written for beginner computer science students. We considered a number of ways to get Python installed on students' computers and ended up settling on [Anaconda Scientific Python Distribution](https://store.continuum.io/cshop/anaconda/) which turned out to be a great option (although nothing is without it's problems, as we'll see later.)

We also made a deal with [Nebula](http://nebulastl.com/), a coworking space on Jefferson Street, to use their conference room. I've got to give Tony all the credit on this one: he hoofed it around town to find the best meeting place for our class and did the hard work of negotiating agreements, plus food for every week. Hats off!

Once we had secured the space and time, we made a launch announcement on @STLPython and our personal Twitter accounts. Several high profile accounts retweeted and shared our message all over the internet, and within three days we had our initial slate of 40 students filled. I thought we would maybe get half of our cap, but apparently there are an enormous amount of people looking to learn to code. I'm still getting emails at least once a week asking how to join or when the next class starts.

## The Class

We went into this knowing that our ideas were not going to be all good. Unsurprisingly, not all of them were! 

### What worked

Anaconda was a major win. We asked people to download the software before class, then simply distributed a couple of USB sticks around the classroom the first night and we were finished in 15 minutes. Everyone had the same environment and tools. Easy!

The thought behind [Light Table](http://www.lighttable.com) as a next-generation IDE means that it works great as a teaching tool. Define something, hit `cmd+enter`, and  see the output right there next to your code. I cranked the font size up so everyone could see, and it suddenly became a giant interactive chalkboard.

Nebula is a great space for a large(ish) group to meet. Jason (the owner) and everyone there were friendly and welcoming, and even agreed to host a regular STL Python meeting while T-REX was moving.

### What was not so great

*How to Think Like a Computer Scientist* turned out to make some assumptions about our students that weren't valid. Specifically, it assumes that students come from a strong mathematics background, which almost none of our class (including me) had. As an example, one of the exercises had students implementing [Fermat's Last Theorem](https://en.wikipedia.org/wiki/Fermat's_Last_Theorem). It was difficult to teach that and then have to explain to my students that yes, their code did in fact work, but there were no known inputs to get it to do that branch of the conditional. Not a great demonstration of conditionals, which the exercise taught. In addition, there were a number of times when the authors taught an older or obscure way to approach a problem and then in a footnote said something along the lines of "it's much simpler if you just do it like this" which nearly always turned out to be the way real world code (the goal) would implement the feature.

We tried to set up Google Hangouts for office hours, thinking that the Hangouts On-Air would work and that people would be able to stream it even if they couldn't join the call. It turns out that office hours need to be much more interactive because beginner students require a tight feedback loop (or at least, tighter than Hangouts On-Air can provide.) We ditched that in favor of [Fuzebox](https://www.fuzebox.com/) which worked a little better.

## For next time

This seemed to be a great experience for everyone who participated. We ended up with about 25% of the people we started out with, but most of those who dropped out emailed us to say "it's not you, I have other commitments on my time and can't finish the course."

For the next class, we'll be making a few changes. First, we'll be trying to find a new textbook. *How to Think* is a good textbook for introductory CS students, but it's not too great for what we're doing and some of the examples and code samples are a little dated. In addition, we want to be teaching our students "real world" Python. *How to Think* alludes a little bit to the idea of something idiomatic Python but didn't define the concept to our satisfaction. If we can't find one we'll write our own (but we'd much prefer to use an established book. If you know of any, **please** drop me a line.) This is intended to be more of a reference material, because...

Second, I'd like to try different kinds of assignments. Practical application of Python being a core tenet of the course it seems necessary to do similar things to what you'd create in real life. Or at least, things the students find interest in doing. The last night of class we did a group exercise on [Markov Chains](https://gist.github.com/BrianHicks/9655533) which everyone in the class got a laugh out of (we used *The Adventures of Sherlock Holmes* as source text.) Things like that will probably play a more central role in future versions of the course.

And lastly, we intended the in-class sessions to be Q&A about the material covered during independent study. That turned out to be an OK fit but throwing someone into a new field and expecting them to ask good questions in a group setting is maybe a little daunting for the learner. We will be carefully considering our course format, and maybe making a few changes there.

To finish up, if you were in the class: thank you for coming. I learned as much from you as (I hope) you did from me and Tony. And of course *tons* of thanks to Tony, who did so much of the administration for this class. We'll see you again soon!
