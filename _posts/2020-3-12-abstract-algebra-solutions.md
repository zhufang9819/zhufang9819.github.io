---
layout: post
titile: 抽象代数习题解答1
category: Abstract Algebra
tag: [solution]
---

## 简介
这是我本人自学抽象代数的记录之一，习题解答，主要是 Artin 的 Algebra （下文我将用Artin替代）一书上的习题，我计划在完成哈佛大学的抽象代数课程作业要求的前提下基于我自己所能尽可能的把此书的习题部分做完整。
<!-- more -->

## 解答
此次课布置了三道题，全部来自于 Artin 的第一章的课后习题。
### 1.1.7

$$
{\left[\begin{array}{ccc}
1 & 1 & 1\\
  & 1 & 1\\
  &   & 1
\end{array}\right]}^{n}
=
\left[\begin{array}{ccc}
1 & 1+n & \frac{n(n+1)}{2} \\
  & 1 & 1+n \\
  &   & 1
\end{array}\right]
$$

用数学归纳法证明很简单，直接证明就好
### 1.1.16
我们设矩阵 $\mathbf{B}$ 是 $\mathbf{I-A}$ 的逆矩阵，那么

$$
\mathbf{B(I+A) = I}
$$

进一步的我们将上式写成除式的形式

$$
\mathbf{B} = \frac{\mathbf{I}}{\mathbf{I+A}} = \frac{\mathbf{I} - \mathbf{A}^{k}}{\mathbf{I-(-A)}} = \mathbf{I} - \mathbf{A} + \mathbf{A}^{2} + \cdots + (\mathbf{-A})^{k-1}
$$

即可以用等比数列求和的形式来进行变式，我们接下来验证这样得到的矩阵 $\mathbf{B}$ 满足

$$
\mathbf{(I+A)B = I}
$$

将所求的$\mathbf{B}$带入上式

$$
\begin{aligned}
\mathbf{(I+A)(\mathbf{I} - \mathbf{A} + \mathbf{A}^{2} + \cdots + (\mathbf{-A})^{k-1}) = I}
\end{aligned}
$$

故由$\mathbf{A}^{k} = \mathbf{0}$ 可以得到矩阵 $\mathbf{I+A}$ 是可逆的

### 1.1.17
可以直接设出待求的矩阵，然后将其与矩阵 $\mathbf{A}$ 相乘，等于对应维数的单位矩阵，再经由矩阵相等即对应矩阵的各元素都相等得到一个线性方程组，来讨论这个线性方程组的解的情况的得出待解矩阵是否存在，具体过程略。