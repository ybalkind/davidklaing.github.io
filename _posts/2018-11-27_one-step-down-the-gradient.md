---
layout: post
title: "One step down the gradient"
description: 
categories: blog
published: false
---

{% include d3_example.html %}

Some friends and I have been working my way through Michael Nielsen's excellent book, [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/). One of the exercises in chapter 1 forced me to flex some math muscles that I haven't used in a long time, so I thought I would write up the answer that my friend Matthew helped me understand. The exercise is this:

> Prove that the choice of $\Delta v$ which minimizes $\nabla C \cdot \Delta v$ is $\Delta v = -\eta \nabla C$, where $\eta = \frac{\epsilon}{||\nabla C||}$ is determined by the size constraint, $\Delta v = \epsilon$. *Hint*: If you're not already familiar with the [Cauchy-Schwarz inequality](https://en.wikipedia.org/wiki/Cauchy%E2%80%93Schwarz_inequality), you may find it helpful to familiarize yourself with it.

The Cauchy-Schwarz Inequality basically just says that the length of the projection of one line on another can be at most as long as the product of the length of those two lines. In other words, the dot product of two vectors can't be bigger than the product of the lengths of those two vectors.

$$|a \cdot b| <= ||a||||b||$$

Subbing in $\nabla C$ and $\Delta v$, we get the following inequality:

$$|\nabla C \cdot \Delta v| <= ||\nabla C|| ||\Delta v||$$

Now, we can make a couple of substitutions. First, we've already said that we want to constrain $||\Delta v||$ to be some value $\epsilon$, so we can replace $||\Delta v||$ on the right-hand side with $\epsilon$:

$$|\nabla C \cdot \Delta v| <= ||\nabla C|| \epsilon$$

Secondly, since we know we want to minimize $\nabla C \cdot \Delta v$, we will need to maximize its absolute value, $|\nabla C \cdot \Delta v|$. Since the magnitude of a dot product is largest when the two vectors are parallel, we know that we'll have to replace $\Delta v$ with $\nabla C$, multiplied by some scalar, $\eta$, whose value will depend on the size constraint $\epsilon$. So let's replace $\Delta v$ on the left-hand side with $\eta \nabla C$:

$$|\nabla C \cdot \eta \nabla C| = ||\nabla C|| \epsilon$$

We can move the $\eta$ outside that dot product, to make it bit easier to look at.

$$\eta |\nabla C \cdot \nabla C| <= ||\nabla C|| \epsilon$$

We'll also turn this into an equality now, since we know that if the left-hand side is less than the right-hand side, it isn't being maximized, like we wanted.

$$\eta |\nabla C \cdot \nabla C| = ||\nabla C|| \epsilon$$

Now, our next step is to solve for $\eta$. This might seem confusing if you're rusty on the dot product. The key is that $a \cdot a = ||a||^2$. Why is this? Well, think about the definition of the dot product. It's the sum of the elementwise products of two vectors:

$$a \cdot b = \sum_ja_jb_j$$

This means that if you take the dot product of a vector with itself, you just get the sum of the elementwise products of that vector with itself:

$$a \cdot a = \sum_ja_j^2$$

If you think back to the Pythagorean theorem, the right-hand side of the above equation might look familiar. It's the square of the length of $a$!

$$|a|=\sqrt{a_1^2+a_2^2 + ... + a_j^2}$$

$$|a|=\sqrt{\sum_ja_j^2}$$

$$||a||^2=\sum_ja_j^2$$

So, we can replace that pesky dot product in our equation, $\nabla C \cdot \nabla C$, with something much more algebraically friendly, $||\nabla C||^2$:

$$\eta |||\nabla C||^2| = ||\nabla C|| \epsilon$$

We can remove the absolute value notation, since the square of anything is always positive:

$$\eta ||\nabla C||^2 = ||\nabla C|| \epsilon$$

And then we can rearrange to solve for $\eta$:

$$\eta = \frac{\epsilon}{||\nabla C||}$$

We've done it! We've shown that 