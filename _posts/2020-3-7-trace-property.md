---
layout: post
title: 矩阵迹的一些性质与应用
category: Matrix Theory
tags: [matrix, algebra]
---

## 简介
矩阵的迹是矩阵对角元素之和，在工程以及计算机领域有比较大的应用，常常会用到一些等价形式或者重要的信息来使得所要解决的问题简化，此文是叙述出一些常用的性质和推论，并且给出必要的证明.

<!-- more -->
### 1.1 迹的定义
矩阵的迹是矩阵的对角线元素之和，给定矩阵$\mathbf{A}$，它的迹可表示为

$$
    tr(\mathbf{A}) = \sum_{i} \mathbf{A}_{ii}
$$

### 1.2 迹的性质

#### 性质 1

$$
tr(\mathbf{AB}) = tr(\mathbf{BA})
$$

#### 证明

$$
\begin{aligned}
tr(\mathbf{AB}) & = \sum_{i} (\mathbf{AB})_{ii} \\
                & = \sum_{i} \sum_{j} \mathbf{A}_{ij} \mathbf{B}_{ji} \\
                & = \sum_{j} \sum_{i} \mathbf{B}_{ji} \mathbf{A}_{ij} \\
                & = \sum_{j} (\mathbf{BA})_{jj} \\
                & = tr(\mathbf{BA})
\end{aligned}
$$

Q.E.D

#### 性质 2