---
layout: page
title: "Week 1 - Supervised Learning"
---
{% include JB/setup %}

Example - Housing price prediction.
-----------------------------------

 - x-axis is size in feet^2
 - y-axis is price ($) in 1000's

Fitting a straight line to data points on graph gives line. Or maybe we want to
fit a polynomial line. (We'll talk later about how to choose which model to
try)

This is also called a regression problem. Get continuous valued output.

In this example, the "right answers" were given to the algorithm. *T* was to
produce more predictive data according to given answers.

Examples - Breast Cancer
------------------------

 - y-axis is malignant or benign? (discrete values)
 - x-axis is tumor size

Task is to figure out if a tumor of a given size is likely to be malignant or
not.

This is a classification problem. We're trying to get a discrete value, 0 or 1.
We could be trying to predict types of tumors, in which case we have 2..n types.

Different way to plot the same data: on one line, with different symbols for
different discrete values (or different colors, whatever. difference is the
point.)

This example uses only one "feature" to predict size. If we had, say, age and
tumor size, we could use symbols as before to graph. More than 2 axes is
difficult. More example features: clump thickness, uniformity of shape,
uniformity of size.

One algorithm we're dealing with in class will be able to deal with an infinite
number of features (can't wait!) How do we deal with that? We use an algorithm
called a support vector machine (SVM). Some mathematical function will let us
calculate them efficiently.
