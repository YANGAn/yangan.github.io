---
layout: post
title:  "Decision Tree"
date:   2021-03-25 08:20:46 +0800
categories: math
use_math: true
---

Let's start from an example, the table below lists the factors that affect people's decision to play golf. 

![Golf_dataset](/image/Golf_dataset.png)

From the table, it is not straightforward how people make the decision. However, the Decision Tree algorithm can give the graph below and I believe it is much clear to you.

![Decision_tree](/image/Decision_tree_model.png)

Yes, that is Decision Tree. The idea is natural, as it is the same as one of human thinking process. Decision trees are commonly used to help identify a strategy most likely to reach a goal, but are also a popular tool in machine learning to do classification.

The mystery I guess is that how each branch is decided. Let's check the mathematics and algorithm behind. In mathematics part, we will introduce **Impurity** concept and in algorithm part, you can see how impurity is applied to achieve the goal.

## Mathematics Behind

**Impurity**

> Impurity is a measure of the homogeneity of the classification, in other words, determines how well a decision tree splits.

## Algorithm

