---
title: Getting started with linear regression using the normal equation
excerpt: excerpt
hero: https://www.disruptivestatic.com/wp-content/uploads/2018/05/machine-learning-ecommerce-blog-1.jpg
alt: alt
date: 2020-06-06 20:33
og:
  image:
    url: /assets/blog/hello-world/cover.jpg
tags:
  - Machine Learning
---

You often want to find parameters that minimise some cost function. One
approach could be using gradient descent. In this article, we will be talking
about another approach called the normal equation.

## Prerequisites

- Linear algebra basics
- Vector basics

## Getting started

$$
\theta = (X^T X)^{-1} X^T y
$$

Wow! One line. Also by using this method, you don't need to do feature scaling.

### Let's verify dimensions

## Octave implementation

```octave
pinv(X'*X)*X'*y
```

## How it works? (optional)

Please feel free to skip this section. This is quite maths heavy. Here is the
outline of the mathematical proof. For brevity, we omit the full proof and only
provide an outline.

## Cautions

- Some of you may have noticed what if $X^T X$ is non invertible (singular) -
- this is the reason we use `pinv` as it always gives us a value for
  $\theta$ Need to compute $(X^T X)^{-1}$ which is slow if $n$ is very large
- since most
  implementations have $O(n^3)$ time complexity ($nxn$ is the dimensions)

