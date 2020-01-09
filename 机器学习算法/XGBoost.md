# XGBoost

## 简介

XGBoost的全称是eXtreme Gradient Boosting（极端梯度增强算法），它是经过优化的分布式梯度提升库，旨在高效、灵活且可移植。XGBoost是大规模并行boosting tree的工具，它是目前最快最好的开源boosting tree工具包，比常见的工具包快10倍以上。在数据科学方面，有大量的Kaggle选手选用XGBoost进行数据挖掘比赛，是各大数据科学比赛的必杀武器；在工业界大规模数据方面，XGBoost的分布式版本有广泛的可移植性，支持在Kubernetes、Hadoop、SGE、MPI、 Dask等各个分布式环境上运行，使得它可以很好地解决工业界大规模数据的问题。

## 原理推导

### 从目标函数开始，生成一棵树

XGBoost和GBDT两者都是boosting方法，除了工程实现、解决问题上的一些差异外，最大的不同就是目标函数的定义。我们从目标函数开始探究XGBoost的基本原理。

#### 学习第 t 棵树

XGBoost是由 k 个基模型组成的一个加法模型，假设我们第 t 次迭代要训练的树模型是ft(x)，则有：

![](imgs/1.jpg)

#### XGBoost的目标函数 

损失函数可由预测值$\widehat{y}$与真实值  进行表示：



