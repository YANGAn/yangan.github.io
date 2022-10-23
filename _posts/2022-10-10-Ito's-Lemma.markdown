---
layout: post
title:  "Ito's Lemma"
date:   2022-10-10 16:20:46 +0800
categories: math
use_math: true
---
Ito's Lemma is the chain rule in stochastic process. It is foundamental technique to simplify stochsastic process formula.

Ito's Lemma is a differential form of Ito-Doeblin formula. Essentially they are the same but in different forms.

> W. Doeblin was a French soldier on the German Front back to 1940's. His work was mailed to French National Academy of Science in 1940 and he died shortly after that. The document only discovered and published in 2000.

**Ito's Lemma**
Let $W(t)$ be a Brownian motion and $f(t,W(t))$ be a function with the existing of $f_t, f_x$ and $f_{xx}$.

$df(t,W(t)) = f_t(t,W(t))dt + f_x(t,W(t))dW(t)+ \frac{1}{2}f_{xx}(t,W(t))dt$

I will see how Ito's Lemma works to derive a simple version of Fokker-Plank Equation.

Assume the function $f(X_t)$, we have

$df = f_xdX_t + \frac{1}{2}f_{xx}dX_t^2$

If $X_t = W(t)$, then

$df = f_xdW(t) + \frac{1}{2}f_{xx}dt$

Take the expectation on both sides, the stochastic part disappears.

$E[df] = \frac{1}{2}E[f_{xx}]dt$

Move $dt$ to the left side,

$\frac{d}{dt}E[f] = \frac{1}{2}E[f_{xx}]$

Assume the density function of $f(X_t)$ is $p(x,t)$ and follow the chain rule, we have the simplified version of Fokk-Plank Equation.

$\frac{\partial{p(x,t)}}{\partial{t}} = \frac{1}{2}\frac{\partial{^2p(x,t)}}{\partial{x^2}}$


> If $dX_t = \mu(X_t)dt + \sigma(X_t)dW(t)$, then the Fokk-Plank Equation is $\frac{\partial{p(x,t)}}{\partial{t}} = (-\frac{\partial{}}{\partial{x}} \mu(x) + \frac{1}{2}\frac{\partial{^2}}{\partial{x^2}}\sigma^2(x))p(x,t)$



