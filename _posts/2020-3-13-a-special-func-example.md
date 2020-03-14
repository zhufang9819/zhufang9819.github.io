---
layout: post
title: A Special Function
category: Real Analysis
tag: [analysis, calculus]
---

## Introduction
Today, I'll introduce a function with some specific properties.

$$
f(x) = \begin{cases}
& \exp({\frac{-1}{x^{2}}}) \quad x \neq 0 \\
& \\
&0 ~~~~~~~~~~~~~\quad x = 0 
\end{cases}
$$

We note that this function is infinitely differentiable on $\mathbb{R}$ and its Taylor expansion on 0 equals to 0. Before proofing these two properties, I'd give a review about differentiable and Taylor expansion first.
<!-- more -->

## Differentiable
First of all, we talk about the single variable condition, we denote a single variable function by $f: \mathbb{R}\to\mathbb{R}$, which is a mapping from $\mathbb{R}$ to $\mathbb{R}$.
    
The function f is *differentiable* at point $a$ if 

$$
\lim_{h\to0} \frac{f(a+h)-f(a)}{h}~\text{exists} 
$$

In this case the limit is denoted by $f'(a)$ and is called the *derivative of $f$ at $a$* (We also say that $f$ is *differentiable* if $f$ is differentiable at $a$ for every $a$ in domain of $f$)  
By the definition of limitation, this form is equivalent to another representation, which is

$$
\lim_{h\to 0} \frac{f(a+h) - f(a) - hf'(a)}{h} = 0
$$

In multivariate situation， as f is function from $\mathbb{R}^{n} \to \mathbb{R}^{m}$, if

$$
\lim_{\mathbf{x}\to \mathbf{x}_{0}} \frac{\mathbf{f(x) - f(x_\text{0}) - A(x - x_{\text{0}})}}{||\mathbf{x} - \mathbf{x}_0||} = 0
$$

where $\mathbf{A}$ is a *linear transformation*, we say that function $\mathbf{f}$ is differentiable on point $\mathbf{x}_{0}$

## Taylor Expansion
### Taylor Polynomial  

$$
P_{n,a}(x) = a_0 + a_1 (x-a) + \cdots + a_n(x-a)^{n}
$$

Where $a_k = \frac{f^{k}(a)}{k!}~(0 \leq k \leq n)$, we note that 

$$
P_{n,a}^{k} (a) = f^{k}(a)\quad \text{for } 0 \leq k \leq n
$$

### 