---
layout: post
title: Complex Analysis Notes 1
category: Complex Analysis
tags: [analysis]
---
## Introduction
 Here is one of my self-taught math courses notes-“Complex Analysis“， I learned this course based on the lecture videos by Steven Miller on [YouTube](https://www.youtube.com/watch?v=bfrIk13rAJ4&list=PL71JUoXcec_mmLm9psjMKo1FYBXS9WHb7) and Stein’s book “Complex Analysis “. I’ll be glad if my notes can help you with learning complex analysis theory. Let’s begin.

<!-- more -->

<hr>
Lecture1 is mostly about the important modules and application of complex analysis and review about some basic calculus.

## 1 Review and Big picture 

### 1.1 Riemann Mapping
**(Rieman mapping theorem)** *Suppose $\Omega$ is proper and smply connected. If $z_{0} \in \Omega$, then there exists a unique conformal map $F: \Omega \to \mathbb{D}$ such that*

$$
F(z_0) = 0 ~~\text{and}~~ F'(z_0) > 0
$$

It will be discussed in subsequent lectures.
### 1.2 Fourier Transform
    
$$
\hat{f} (y) = \int_{-\infty}^{+\infty} f(x) e^{-2\pi i x y} \mathrm{d} x 
$$
    
### 1.3 Factorial

Factorial in $\mathbb{N}$

$$
n!= n \times (n-1) \cdots 3 \times 2 \times 1
$$

Gamma Function

$$
    \Gamma (s) = \int_{0}^{+\infty} e^{-x} x^{s-1} \mathrm{d}x
$$

1. $\Gamma (n+1) = n!$
2. $\Gamma (s+1) = s~\Gamma(s) \quad \Re({s}) > 0$ 
3. $\Gamma(\frac{1}{2}) = (-\frac{1}{2})! = \sqrt{\pi}$

### 1.4 Number Theory

#### Riemann-Zeta Function

$$
\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^3} = \prod_{p~\in~\text{primes}}(1 - \frac{1}{p^{s}})^{-1} \quad \Re({s}) > 1
$$

1. $\lim_{\epsilon \to 1^{+}} \zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n}$
2. $\zeta({2}) = \sum_{n=1}^{\infty} \frac{1}{n^2} = \frac{\pi^{2}}{6} = \prod_{p} \frac{p^2}{p^2 - 1}$

### 1.5 Moments

$$
M_{k} = \int_{-\infty}^{+\infty} x^{k} f(x) \mathrm{d} x
$$

*Moments* may not exist.

## 2 Differences between Real and Complex
Let $f: \mathbb{R} \to \mathbb{R}$ be a diffentiable function and let also $g: \mathbb{C} \to \mathbb{C}$ be a complex differentiable function , and let $h: \mathbb{R}^{2} \to \mathbb{R}^{2}$ be a differentiable function.

|Properties | $\mathbb{R}$ | $\mathbb{C}$ |
|:--------:| :------------:|:------------:|
|If $f$ is differentiable, then f is <br> infinitely diffentiable|No <br> $f(x) = x^{3}\sin (\frac{1}{x})$|Yes|
|function equals its Taylor series <br>in some neighborhood at point where differentiable|No | Yes|
|The function may be bounded without being <br>identically constant|Yes<br> $f(x) = \sin x$|No|
|The line integral of our function along a closed curve must be zero|No|Yes|