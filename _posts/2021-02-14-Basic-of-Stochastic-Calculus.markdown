---
layout: post
title:  "Basic of Stochastic Calculus"
date:   2021-02-14 16:20:46 +0800
categories: math
use_math: true
---
**Brownian Motion**

In discrete format, the concept of random walk is relatively easy to accept, one time one uniform step, up or down. In the macroworld, there is seldom change/motion which is discrete. The Brownian Motion can be seen as the continuous motion with uniform speed, where the direction is up or down and can change anytime. Based on this understanding, naturally there are two charaticstics of the Brownian Motion $W(t), t\geq 0$:

* $ W([t_1,t_2]) = W(t_2) - W(t_1) $ is independent from $W([t_i,t_j])$ if the time is not overlapped

* $ W([t_1,t_2]) $ is normal distributed, i.e. $N(0,t_2-t_1)$

The above is also how the Brownian Motion is defined. Just a word on probability space $(\Omega, \mathcal{F}, \mathbb{P})$, and this can simply understand as (All the outcomes, Rule, Probability).

For the problem of Brownian Motion, it is solved or becomes easier if the form of $W([t_1,t_2])$ emerges.

**Martingale Property**

$\mathbb{E}[W(t)\|\mathcal{F}(s)] = W(s), s< t $

The martingale property is important but it might be more useful to check **Exponential Martingale Property** and **Markov Property**.

Exponential Martingale Property: $\mathbb{E}[Z(t)\|\mathcal{F}(s)] = Z(s), s< t $ where $Z(t)=exp \[ \sigma W(t)-\frac{1}{2}\sigma^2t \]$




