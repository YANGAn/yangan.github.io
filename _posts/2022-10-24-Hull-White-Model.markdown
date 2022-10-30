---
layout: post
title:  "Hull White Model"
date:   2022-10-10 16:20:46 +0800
categories: math
use_math: true
---
The fixed income market offers bonds, and the interest rate derivatives are the pre-eminent market among the OTC transactions. This contributes from the nature of corporate financing.

> Global fiexed income markets outstanding is \\$126.9 trillion in 2021, while global equity market capitalization is \\$124.4 trilion in 2021.

> The notional value of outstanding interest rate derivative is \\$440 trillion, while the total derivative is \\$610 trillion in 2021.

The term structure is the specific part from derivatives on equity market. Hull White model is one of the earliest model that can model the term structure. It is popular because it is non-aribtrage and relatively easy to calibrate.

It models the short rate and becomes one factor model if the mean reversion is pre-determined.

**Short Rate**

Let $P(t,T)$ be a bond price with the maturity at $T$. The relationship with forward rate $f(t,T)$ is as below.

$P(t,T) = e^{-\int_t^T{f(t,u)du}}$

The forward rate is the rate over the period of $[t,T]$ and observed from market if $t$ is the current time point. The short rate $r(T)$ is $f(T,T)$, a future instantenous rate.

$P(t,T) = \mathbb{E}e^{-\int_t^T{r_u du}}$

**Hull White Model**

$dr(t) = k[\theta(t) - r(t)]dt +\sigma(t)dW(t)$

Let $r_t = x_t +\phi(t)$, then $\theta(t) = \phi(t) + \frac{1}{k}\frac{d\phi(t)}{dt}$ and the above process becomes the below

$dx_t = -kx_tdt + \sigma(t)dW(t)$

Solve it by the following steps:

$dx_t + kx_tdt = \sigma(t)dW(t)$

$e^{kt}(dx_t + kx_tdt) = e^{kt}\sigma(t)dW(t)$

$de^{kt}x_t =e^{kt}\sigma(t)dW(t)$

Integrate by $t$ from $t$ to $u$,

$\int_t^u de^{kv}x_{v} =\int_t^u e^{kv}\sigma(v)dW(v)$

$x_u = e^{-k(u-t)}x_t + \int_t^u e^{-k(u-v)}\sigma(v)dW(v)$

$r_{u} = \phi(u) + e^{-k(u-t)}x_t + \int_t^u e^{-k(u-v)}\sigma(v)dW(v)$

[Comment]: The above formula gives the explicit solution of short rate $r(u)$.

Integrate by $u$,

$\int_t^T r_{u} du = \int_t^T \phi(u) du + \int_t^T e^{-k(u-t)}x_t du+ \int_t^T \int_t^u e^{-k(u-v)}\sigma(v)dW(v)du$

$\int_t^T r_{u} du = \int_t^T \phi(u) du + \beta(t,T) x_t + \int_t^T \sigma(v)\beta(v,T)dW(v)$, 

where $\beta(t,T) = \frac{1}{k}(1-e^{-k(T-t)})$

So the bond price is

$P(t,T) = \mathbb{E} e^{-\int_t^T r_{u} du}$

$P(t,T) = \mathbb{E} e^{-[\int_t^T \phi(u) du + \beta(t,T) x_t + \int_t^T \sigma(v)\beta(v,T)dW(v)]}$

By Exponential Martingale Property,

$P(t,T) = e^{-[\int_t^T \phi(u) du + \beta(t,T) x_t - \frac{1}{2}\int_t^T \sigma^2(v)\beta^2(v,T)dv]}$

$dP(t,T) = P(t,T)*[\phi(t)dt - d(\beta(t,T)x_t) - \frac{1}{2}\sigma^2(t)\beta^2(t,T)dt]$

By Ito's Lemma on $x_t$,

$dP(t,T) = P(t,T) * [r_tdt - \sigma(t)\beta(t,T)dW(t)]$

The above formula give the relationship between the short rate $r(t)$ and the bond price $P(t,T)$.


-------

Reference: Choong Tze Chua, Dean Foster, Krishna Ramaswamy and Robert Stine, A Dynamic Model for the Forward Curve, 2005.

[Comment]: The structure of forward rates for fixed maturity loans to begin at various dates in the future can be inferred from the prices of Treasury securities or directly observed from the extremely active Eurodollar Futures market. The constellation of these rates (or of the related yields) plays a central role in the allocation of capital. The random behavior of this “yield curve” – or the relationship between the yields and the term to maturity – is a subject of considerable theoretical and empirical study. Yield curves have traditionally been modelled in one of two ways: equilibrium models and no-arbitrage models. Equilibrium models such as the Vasicek model (1977) and the Cox-Ingersoll-Ross model(1985) define stochastic processes driven by a small number of forcing factors. Once these processes are defined, the forward curve and its evolution can be derived either under various assumptions for the risk premia or from a more fundamental model that begins with preferences and imposes market clearing conditions. Empirically, however, these models do not fit the observed forward curve well on any given day. In fact, the fit is often so poor that the differences between the empirical and theoretical values can be construed as model mis-specification rather than random pricing errors.

[Comment]: In contrast, no-arbitrage models are calibrated to fit the observed forward curve perfectly on a given day. This approach to modelling the term-structure was pioneered by Ho and Lee (1986). Hull and White(1990) also built a no-arbitrage model that extended the Vasicek model to fit the initial term-structure. Other important contributors to the no-arbitrage model literature include Black, Derman and Toy(1990) and Heath, Jarrow and Morton (HJM)(1992). HJM derived a framework for the arbitrage-free evolution of the entire forward curve, starting from the currently observed forward curve. The time series dynamics of the forward curve evolution are constrained by the current shape of the curve. Also, these models are forced to fit measurement errors in the observed term structure thereby generating erroneous implications for the time-series evolution. This has led some authors to argue that by forcibly calibrating the entire curve to the observed rates, arbitrage-free principles could be violated (see Backus, Foresi and Zin(1998)).

[Comment]: There have been several new developments in term-structure modelling in the form of market models and stochastic string models. Market models seek to model observable quantities such as the London Interbank Offered Rates (LIBOR) directly within the framework of HJM. Brace, Gatarek and Musiela(1997) and Miltersen, Sandmann and Sondermann(1997) proposed the BGM model that falls into this category. Because these models can be calibrated using observed market rates instead of proxies, they can be estimated accurately. Stochastic string models were first developed by Kennedy(1994), who modelled the forward curve as a Gaussian random field. Goldstein(2000), Santa Clara and Sornette(2001) and Collin-Dufresne and Goldstein(2003) later proposed similar models that allow for correlated strings of shocks to the forward rate curve. In stochastic string models, instantaneous forward rates of differing maturities are driven by their own shocks that can be correlated with those of neighboring maturities. Stochastic string models can fit any day’s cross section of bond prices perfectly without any need for measurement error. Thus when measurement errors are in fact present these models may over-fit the data.



[Comment]: https://zhuanlan.zhihu.com/p/142238913