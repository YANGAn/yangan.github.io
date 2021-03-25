---
layout: post
title:  "Basic of Stochastic Calculus"
date:   2021-02-14 16:20:46 +0800
categories: math
use_math: true
---
## Brownian Motion

In discrete format, the concept of random walk is relatively easy to accept, one time one uniform step, up or down. In the macroworld, there is seldom change/motion which is discrete. The Brownian Motion can be seen as the continuous motion with uniform speed, where the direction is up or down and can change anytime. Based on this understanding, naturally there are three charaticstics of the Brownian Motion $W(t), t\geq 0$:

* $W(0) = 0$

* $ W([t_1,t_2]) = W(t_2) - W(t_1) $ is independent from $W([t_i,t_j])$ if the time is not overlapped

* $ W([t_1,t_2]) $ is normal distributed, i.e. $N(0,t_2-t_1)$

The above is also how the Brownian Motion is defined. Just a word on probability space $(\Omega, \mathcal{F}, \mathbb{P})$, and this can simply understand as (All the outcomes, Rule, Probability). Specifically, "All the outcomes" mean all the Brownian Motion paths.

For the problem of Brownian Motion, it is solved or becomes easier if the form of $W([t_1,t_2])$ emerges.

**Martingale Property**

$\mathbb{E}[W(t)\|\mathcal{F}(s)] = W(s), s< t $

The martingale property is important but it might be more useful to check Exponential Martingale Property and Markov Property. 

**Exponential Martingale Property** 

$\mathbb{E}[Z(t)\|\mathcal{F}(s)] = Z(s), s< t $ where $Z(t)=e^{ \sigma W(t)-\frac{1}{2}\sigma^2t }$ 

The exponential martingale is a more common form of Martingale in financial mathematics.

> Remark: Stopping time & Reflection Principal

**Markov Property** 

$\mathbb{E}[f(W(t)\|\mathcal{F}(s)]=g(W(s))$

where $g(x)$ is defined as below:

[Comment]: #is useful when we solve stochastic calculus problems. Put an example here

$g(x) = \mathbb{E}[f(W(t)-W(s)+x)]=\frac{1}{\sqrt{2\pi(t-s)}}\int_{-\infty}^{\infty} f(w+x) e^{-\frac{w^2}{2(t-s)}} dw$

The process of proof is very important as it introduces **Transition Density** $p(\tau, x,y)$ which is the probability density from state $x$ to state $y$ with the time period $\tau$. The function $g(x)$ can be rewritten as 

$g(x)= \frac{1}{\sqrt{2\pi\tau}}\int_{-\infty}^{\infty} f(y) e^{-\frac{(y-x)^2}{2\tau}} dy = \int_{-\infty}^{\infty} f(y)p(\tau, x,y)dy$


> Remark: It links to Stopping time problem. (This will be discussed in an individual post.)

## Derivative of $W(t)$

The derivate $\frac{d}{dt}W(t)$ doesn't exist. Wait! You mentioned that $W(t)$ is normal distributed and normal distribution is continuous! 

> Please note that the outcome of Brownian Motion $W(t)$ is normal distributed, NOT the process against the time $t$.

Against the time, Brownian Motion is just Brownian Motion, similar to random walk. Then how is the deerivative of $W(t)$ defined? The answer is **Quadratic Variation**.






