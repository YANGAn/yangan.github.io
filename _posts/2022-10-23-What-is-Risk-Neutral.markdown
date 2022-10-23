---
layout: post
title:  "What is Risk Neutral"
date:   2022-10-10 16:20:46 +0800
categories: math
use_math: true
---
From the words Risk Neutral, it tells the investor has no risk preference. That's correct, but what does it mean? It means two practical points below to me:

* Expected rate of return is risk free rate
* The spot price is the expectation of the asset/underlying

That sounds great for pricing any contingent claim as the asset/underlying is easily predicted. But wait, for a stock, why is the expected rate of return risk free rate? It doesn't have to, but adjusting the probability can make it.

| Rate of return  | 16%       | |Rate of return  | 3%        |
| :---            |  :----:   | |:---            |  :----:   |
| Prob $p_1$: 56% | 2         | |Prob $p_1$: 50% | 2         |
| Prob $p_2$: 44% | 0         | |Prob $p_2$: 50% | 0         |
| Expected price  | 0.97      | |Expected price  | 0.97      |

Although the probability is adjusted, the market expected price still matches. In practice, the probability is derived from market price and this process is called calibration.

Let us introduce some concepts in non-technique way.

* **Numeraire**: a positive non-dividend paying asset, which can be seen as a benchmark asset
* **Measure**: a probability distribution
* **Change of measure**: change the mean of the distribution, but the volatility keeps.

The rate of return and the probability can be adjusted, in the above language, the benchmark (Numeraire) and the probability distribution (Measure) can be changed for the calculation convinience.   



