---
layout: page
title: "Week 1 - Supervised Learning"
---
{% include JB/setup %}

In unsupervised learning we're not told what each data point is (in the case of
tumors, no malignant or benign.) The algorithm would have to figure out how to
split the points up. This is called a clustering algorithm. These are used in
places like Google News.

Users of unsupervised learning
------------------------------

 - Organizing computer clusters by figuring out which machines work together
   (and then placing them closer)
 - Social network analysis. Who knows who?
 - Market segmentation. Automatically discover market segments.
 - Astronomical data analysis. Figure out how galaxies are formed.

Cocktail party problem
----------------------

Given two speakers, and two microphones (at two different distance from the two
speakers,) the two microphones will record slightly different versions of the
speakers. The cocktail party algorithm can separate the two speakers into
separate recordings.

Behold, the cocktail party algorithm (in octave):

    [W,s,v] = svd((repmat(sum(x.*x,1),size(x,1),1).*x)*x');


Octave
------

Good for prototyping. Very fast to prototype learning algorithms. A lot of
people will make in Octave, and then in Java/C++/whatever. Ng says "trust me on
this one."

So, on OSX: `brew install octave`.
