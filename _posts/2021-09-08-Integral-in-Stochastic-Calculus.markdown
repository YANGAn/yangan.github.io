---
layout: post
title:  "Integral in Stochastic Calculus"
date:   2021-09-08 16:20:46 +0800
categories: math
use_math: true
---

Preliminary article: Basic of Stochastic Calculus

The Brownian Motion $ W(t) $ is not differentiable, however similar to the definition of quadratic variation, the integral of $W(t)$ can be defined as the sum of value in each partition of the time period, which is called Ito's Integral:
$$
I(t) = \int_{0}^{t} \Delta (u) dW(u) = \lim_{n \to \infty}\sum_{j=0}^{k-1} \Delta(t_j)[W(t_{j+1})-W(t_j)]
$$

The Ito's integral satifies the following properties:

* **(Maringale)** $I(t)$ is a martingale

* **(Ito's isometry)** $\mathbb{E}I^2(t) = \mathbb{E}\int_{0}^t\Delta^2(u)du$

* **(Quadratic variation)** $\[I,I\](t) = \int_{0}^t\Delta^2(u)du$.

It is good to notice the difference of quadratic variation and the variance of the process $I(t)$. The quadratic variation is path-dependent, while the variance of $I(t)$ is an average over all possible paths of the quadratic variation.

Similar to Riemann integral, the Ito's integral is calculated from a partition of a time interval $[0,t]$. What does the Brownian motion $W(t)$ do in the integral? For illustration purpose, assume that $\Delta (t)$ is not a function of $W(t)$ but just $t$. The integral will be similar to the graph as below and takes into the consideration of the distribution of $W(t)$ at the time point $t$. In other words, the integral is a multiplication of $\Delta (t)$ and a normal distributed density along the time $t$. 

![Integral_Ito](/image/Integral_Ito.png)

In the case that $\Delta (t)$ is a function of $W(t)$, which is much common in stochastic calculus, it is more complicated but it follows the idea elaborated above.

When we are given a stochastic process, how can we integrate it into an expressive equation? 
$$ dS(t) = a(t) dt + b(t) dW(t) $$
The answer is that we don't need to do it, but we should be used to leave it and view it as some distribution, usually it is normal distribution. Let's explain it.

$$
\begin{align*}
 S(T) &= S(0) + \int_{0}^{T} a(t) dt &+ \int_{0}^{T} b(t) dW(t) \\
    &= S(0) + \int_{0}^{T} a(t) dt &+ \lim_{n-> \infty}\sum_{i=1}^{n} b(t_{i-1}) (W(t_{i}) - W(t_{i-1})) \\
    &= [\text{mean}] &+ [\text{sum of independent normal distributions}] \\
    &= [\text{mean}] &+ [\text{a normal distribution}]
\end{align*}
$$

From the above, there are two parts: the 'mean' part is ordinary calculus; and the 'normal distribution' part. So what is $S(T)$? It's a normal distribution with the mean $S(0) + \int_{0}^{T} a(t) dt$ and the derivation of $\int_{0}^{T} b(t) dW(t)$. If $b(t)$ is constant $b$, the latter part is $b W(T)$ with the deviation of $b \sqrt{t}$.

If $b(t)$ is $W(t)$, we have
$$ \int_{0}^{T} W(t) dW(t) = \frac{1}{2} W^2(T) - \frac{1}{2}T
$$
If $b(t)$ is in other form, the integral can be get similarly to Riemann sum, by $\lim_{n-> \infty}\sum_{i=1}^{n} b(t_{i-1}) (W(t_{i}) - W(t_{i-1}))$.




