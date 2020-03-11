---
layout: post
title: mooc 算法分析测试
category: Data Structure and Algorithms
tags: [Dsa, Mooc]
---

## 简介

这是疫情期间学校所借助中国大学mooc上的课程对应单元测试的习题解，无标准答案，错误在所难免，敬请指正
<!-- more -->
### 第一周 基础知识 (1)

#### 第一题

递减有序且不相等，即 $a_m > a_n~(m < n)$， 则第 $i$ 趟需要 $n - i$ 次交换

$$
\sum_{k=1}^{n} (n-k) = 1 + 2 + \cdots + n-1 = \frac{n(n-1)}{2}
$$


#### 第二题

$$
2^{t} + 2^{t-1} + \cdots + 1 = \frac{1(1-2^{t+1})}{1-2} = 2\times2^{t} - 1 = 2n - 1
$$

#### 第三题

记 $p$ 为取到第一个元素的概率，由题设，我们可以归纳出取到第 $k$ 个元素的概率为 $\frac{p}{2^{k-1}}$ ，记其为$a_{k}$，如果考虑元素不合法的情况，即不在这 $n$ 个列表元素之中，那么我们需要假定取到这些不合法元素的概率是相等的，那么在这些不合法位置的元素的概率是 $\frac{1-\sum_{k}a_{k}}{n+1}$，记为$b_{k}$，在这种情况下的平均时间复杂度是

$$
A(n) = \sum_{k=1}^{n} ka_{k} + \sum_{k=1}^{n+1} k b_k 
$$

这是算不出来一个常量的，因为 $p$ 未知，如果我们不考虑不合法的询问，则有$\sum_k a_k = 1$，即

$$
p + \frac{p}{2} + \cdots + \frac{p}{2^{n-1}} = 1
$$

我们有

$$
p~\frac{1 - (\frac{1}{2})^{n}}{1-\frac{1}{2}} = p(2 - \frac{1}{2^{n-1}}) = 1
$$

当$n \to \infty \Longrightarrow p = \frac{1}{2}$

进一步的我们可以使用混合数列错位相减求解出 $A(n)$

$$
A(n) = \sum_{k=1}^{n} k a_{k} = \frac{1}{2}(~4-(\frac{1}{2})^{n-2}~) = 2 \quad (n \to \infty) 
$$

#### 第四题
堆排序是 $\mathcal{O}(n\log n)$，其他最坏情况下都是 $\mathcal{O} (n^ {2})$

#### 第五题
1. $n! = \mathcal{\omega} (2^{n})$
2. $\log (n!) = \mathcal{O} (n)$ 
3. $\log (n!) = \mathcal{O} (n^{2})$
4. $n! = \mathcal{o} (n^{n})$


对于 1，可以使用 Stirling 公式推导出$n!$ 和$\sqrt{2\pi n}(\frac{n}{e})^{n}$同阶，所以 1 正确，对于 2，我们证明一个结论

$$
\log (n!) = \mathcal{\Theta} (n \log n)
$$
#### 证明

$$
\begin{aligned}
\lim_{n\to \infty} \frac{\log (n!)}{n\log n} & = \lim_{n\to\infty} {\frac{\log (n!)}{\log \sqrt{2\pi n}(\frac{n}{e})^{n}}}  {\frac{\log \sqrt{2\pi n}(\frac{n}{e})^{n}} {n \log n} }\\
                                             & = \lim_{n\to \infty} \frac{\log \sqrt{2\pi n} + n(\log n - \log e) }{n\log n} \\
                                             & = \lim_{n\to \infty} \frac{\frac{1}{2}\log{2\pi} + \frac{1}{2} \log n + n \log n + n \log e}{n \log n} \\
                                             & = 1

\end{aligned}
$$

Q.E.D

所以 2 错误，3 正确，对于 4，$n !$ 最多到$n-1$阶，故4正确

#### 第六题

极限 $\lim_{n\to \infty} \frac{n \sin (n)}{n}$ 不存在，则不确定
#### 第七题

1. $~2^{\sqrt{2 \log n}} = \mathcal{O}(2^{\log \sqrt{n}})$
2. 可用 1 的方法，判断其错误
3. 可以用第五题的结论判断其正确
4. $(\log n) ^{\log n} = \mathcal{O}(n^{\log \log n})$
 
对于1, 令 $\sqrt{n} = t$ 则有

$$
\lim_{n\to\infty} \frac{\sqrt{2 \log n}}{\log \sqrt{n}} = \lim_{t\to \infty} \frac{\sqrt{4 \log t}}{\log t} = 0
$$

故 1 正确，2，3 已在题号旁说明，对于 4 ，我们可以对$(\log n) ^{\log n} = n^{\log \log n}$
对两边取对数，分别得到 $\log n (\log \log n)$和 $\log \log n (\log n)$，两者显然是相等的，故 4 正确

#### 第八题
#### 第九题
#### 第十题
以上三题参考[1.8节课件定理1](https://www.icourse163.org/spoc/learn/HNNY-1451736183?tid=1452177464#/learn/content?type=detail&id=1221818884&cid=1232517219)

### 第二周 基础知识 (2)

### 第三周 分治策略 (1)
### 第四周 分治策略 (2)