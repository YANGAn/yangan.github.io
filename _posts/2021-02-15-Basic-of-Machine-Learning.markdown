---
layout: post
title:  "Basic of Machine Learning"
date:   2021-02-15 09:20:46 +0800
categories: math
use_math: true
---

This article helps you understand the concept of Machine Laerning. It comes in the format of FAQ (Frequently Asked Questions), and focuses on the mysteries that I had during the study of machine learning. The general ideas of algorithms are also introduced here but not in details of mathematical basic or implementation.

**What's the ML (Machine Learning)?**

ML: the computer algorithm with data feed to achieve self-evolving solution. A video of the introduction to Machine Learning? ([2 minutes video](https://youtu.be/QghjaS0WQQU))

>Machine learning is the study of computer algorithms that allow computer programs to automatically improve through experience.
>
>   --- by Tom Mitchell, McGraw Hill, 1997

**What's the difference from AI (Artificial Intelligence)?**

AI: general concept to allow machines to act like humans. In this sense, AI is the intergated product of "smart" machine, which can include the algorithm, the soft/hard-ware and the interaction with human or environment.

**What's the difference from Statistics / Data Mining?**

The common part is data driven. Statistics / Data Mining study the patterns, relationships or anomalies of data / large data set. This requires human intervention and decision making. Machine Learning fully/partially cuts the human intervention.


**The classification of Machine Learning**

* Supervised Learning - labelled
* Unsupervised Learning - non-labelled
* Reinforcement Learning - interaction/dynamics to maximize the cumulative reward (e.g.Go game, the next step depends on the interaction of the opponent, and there is no sure win until the last stage but the highest chance to win.) A fun example is the [Mario video](https://youtu.be/qv6UVOQ0F44)

> *Deep Learning, also known as deep neural learning or deep neural network.* 
>> *It's not one of the classification of problems that Machine Learning is going to solve. Instead, Deep Learning is an algorithm of neural network to solve any problem it can.*

**The common algorithms**

* Regression - *linear relationships with (transformed) features*
* Decision Tree - *flowchart with conditions on features*
* K-Nearest Neighbors (KNN)
* Random Forest
* Gradient Boosting (GBT)
* Support Vector Machine (SVM)
* Neural Network

# ANNs - Artificial Neural Networks
Because of the requirement of little human invention, the criteria of justifying a model becomes very importance and must be quantifiable/measurable. You will see the measurement how good the model is plays a very important part of Machine Learning. Take regression as an example, in Statistics, the practitioner focuses on the relationship between dependent variable and independent variables/features and further the economic explanation/understanding. However, in Machine Learning, this relationship is driven by the goodness of fitting and the prediction power gives the final call. 

Reference: Nelson Liu, Ngee Ann Polytechnic, Introduction to Machine Learning, 2021