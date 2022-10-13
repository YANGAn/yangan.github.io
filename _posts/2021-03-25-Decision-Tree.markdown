---
layout: post
title:  "Decision Tree"
date:   2021-03-25 08:20:46 +0800
categories: math
use_math: true
---

Decision Tree is a supervised learning approach. The model is a predictive model and usually for classification, where the target variable is discrete. Although it also can be used for continuous target variable, the prediction is less effective.

The decision tree is intuitive and usually the softwares provide the visualisation. One benefit of the process is that it can handle the dependent variables, both discrete and continous.

Let's check one example, the table below lists the factors that affect people's decision to play golf. 

![Golf_dataset](/image/Golf_dataset.png)

From the table, it is not straightforward how people make the decision. However, the Decision Tree algorithm can give the graph below and I believe it is much clear to you.

![Decision_tree](/image/Decision_tree_model.png)

Yes, that is Decision Tree. The idea is natural, as it is the same as one of human thinking process. Decision trees are commonly used to help identify a strategy most likely to reach a goal, but are also a popular tool in machine learning to do classification.

The mystery I guess is that how each branch is decided. Let's check the mathematics and algorithm behind. In mathematics part, we will introduce **Impurity** concept and in algorithm part, you can see how impurity is applied to achieve the goal.

## Mathematics Behind

**Impurity**

> Impurity is a measure of the homogeneity of the labels, in other words, determines how well a decision tree splits.

**Entropy**

> Entropy is a measure of chaos in the dataset, with weighted entropy to evaluate the splits.

## Algorithm

CART (Classification and Regression Trees) — This makes use of Gini impurity as the metric.
ID3 (Iterative Dichotomiser 3) — This uses entropy and information gain as metric.

Gini impurity is defined as

$Impurity = 1 - Gini = 1 - \sum_i{P_i^2}$

where $P_i$ is the probability of one category in the group/subgroup.

Group:
* Play: 9, Prob: 9/14
* Don't Play: 5, Prob: 5/14
* Gini = $(9/14)^2+ (5/14)^2$
* Impurity = 1 - Gini = 1- 0.54 = 0.46

Subgroup (weighted impurity):
* Outlook = 5/14* Sunny Impurity + 4/14* Overcast Impurity + 5/14 * Rain Impurity = 5/14 * 0.48 + 4/14 * 0 + 5/14 * 0.48 = 0.34
* Windy = 6/14 * Windy Impurity + 8/14 * Non-windy Impurity = 6/14 * 0.38 + 8/14 * 0.5 = 0.43

When it comes to continuous variables, the technique of regression tree is used in the algorithm, like CART, ID3. The regression tree determins threshold(s) by the same measure of impurity. There are different methods to determine the threshold(s). More details can be found in the paper *Efficient Determination of Dynamic Split Points in a Decision Tree* by Microsoft Research.
* If the threshold is 85, Humidity = 0.44
* If the threshold is 80, Humidity = 0.39
* If the threshold is 70, Humidity = 0.45

Similar regression tree can be done on the feature Temperature. However, you will find the feature Outlook mostly reduces the impurity. Thus it is chosen as the first top leaf on the tree. Similar steps will produce the children leaves.

## Local optimum

It is easy to note that the locally optimal decisions are made at each leaf in the above algorithms. This also makes the decision tree is not robust, i.e. a samll change in the training data can result in a large change in the tree. In this case, you might consider other algorithms such as Dual Information Distance (DID).
