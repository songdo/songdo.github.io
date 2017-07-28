---
layout: post
title: 图像检索：拓展查询(Query Expansion)
categories: [Image Retrieval]
tags: 拓展查询
---







## 特征表达


## 特征索引


## 评价指标



对于Oxford Building图像数据库，mAP的计算过程有必要详细介绍一下。Oxford Building的groundtruth有三类：good, ok和junk。对于某个检索结果，如果它在good和ok中，则被判为是与查询图像相关的；如果在junk中，则被判为是不相关的。我们可以细致的阅读一下Oxford Building的mAP计算代码：



## 查询拓展对mAP的提升

![drawing](http://ose5hybez.bkt.clouddn.com/2017/0205/qe_map_zpsbat8vy5x.PNG)

在不做Query Expansion的时候，即top@K=0时，mAP为61.91%。因为查询属于库内查询，所以top@K=1时，仍然是查询向量本身，故结果与top@K=0是一样的。从实验的结果可以看出，Query Expansion确实能够提升检索的精度，在top@K=3的时候，取得了最高的检索精度。相比于不做Query Expansion，Query Expansion可以提高4%-5%的检索精度。

所以，**在实际中，做Query Expansion完全是有必要的，一则是它实现简单，二则是它提升的效果还是比较明显的**
