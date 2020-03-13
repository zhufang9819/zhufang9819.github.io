---
layout: post
title: Abstract Algebra Notes
category: Abstract Algebra
tag: [algebra]
---
## Introduction
 Here is one of my self-taught math courses notes-"Abstract Algebra"， I learned this course based on the lecture videos on [Harvard U](http://matterhorn.dce.harvard.edu/engage/ui/index.html#/1999/01/82345) and Michael Artin’s book "Algebra". I’ll be glad if my notes can help you with learning abstract algebra. Let’s begin.

<!-- more -->

## Lecture 1
Part 1 of the first lecture is mainly about the relationship between linear transformation and matrix in linear algebra and some basic properties about matrix. In part 2， the professor put forward the concept of Group and displayed some Group examples including the abelian group and so on.

### 1. Review of Linear Algebra
the set of $n$ by $n$ matrices $M_n(\mathbb{R})$
#### 1.1 Addition and Multiplication
$\mathbf{A, B} \in M_n({\mathbb{R}}) \Rightarrow \mathbf{A+B = B+A}$ and the $i-j$ entry of the multiplication of matrices:

$$
(\mathbf{AB})_{ij} = (\mathbf{C}_{ij}) = \sum_{k=1}^{n} \mathbf{A}_{ik} \mathbf{B}_{kj}
$$

#### 1.2 Invertibility
If matrix $\mathbf{A}$ is *invertible*, we have

$$
\exists~\mathbf{B} \in  M_n(\mathbb{R}) \longrightarrow \mathbf{AB = BA = I}
$$

#### 1.3 Determinant
##### 1.3.1 Definition

$$
\det (\mathbf{A}) = \sum_{n!~\text{terms}} (\pm 1) ~\text{products of}~n ~\text{matrices entries}
$$

$$
\mathbf{A} ~\text{is invertible} \longleftrightarrow \det({\mathbf{A}}) \neq 0
$$

### 2. Group

#### 2.1 Definition
##### 2.1.1 Binary Operation

1. A *binary operation* $\star$ on set $G$ is a function $\star: G \times G\to G$. For any $a, b \in G$, we shall write $a \star b$ for $\star(a,b)$.
2. A *binary operation* $\star$ on set $G$ is *associative* if for all $a, b, c \in G$, we have $a\star(b\star c) = (a\star b)\star c$
3. If $\star$ is a binary operation on a set $G$ we say elements $a, b~\text{of}~G$ *commute* if $a\star b = b \star a$. We say $\star~\text{(or}~G ~)$ is *commutative* if for all $a, b \in G$, $a \star b = b \star a$

##### 2.1.2 Group
A *group* is an orderd pair ($G, \star$) where $G$ is a set and $\star$ is a binary operation on $G$ satisfying the following axioms:
1. $(a\star b) \star c = a \star (b \star c)$, for all $a, b, c\in G$, i.e, $\star$ is associative.
2. There exists an elments $e$ in $G$, called an *identity* of $G$, such that for all $a \in G$, we have $a \star e = e \star a = a$,
3. For each $a \in G$ there is an element $a^{-1}$ of $G$, called an *inverse* of $a$, such that $a \times a^{-1} = a^{-1} \times a = e$

The group $(G, \star)$ is called *abelian* ( or *commutative* ) if $a \star b = b \star a$ for all $a, b \in G$.

#### 2.2 Examples

##### 2.2.1 General linear group $GL_{n} (\mathbb{R})$
###### Definition
The $n \times n$ *general linear group* is the group of all invertible $n \times n$ matrices. It is denoted by

$$
GL_{n}(\mathbb{R}) = \{~n \times n ~\text{matrices}~ \mathbf{A} ~\text{with}~ \det (\mathbf{A}) \neq 0 ~\}
$$

##### 2.2.2 Abelian
1. $(\mathbb{Z}, +)$: the integers, with addtion;
2. $(\mathbb{R}, +)$: the real number, with addtion;
3. $(\mathbb{R}, \times)$: the nozero real numbers, with multiplication;
##### 2.2.3 Symmetric group
In a set $S =$ Maps$(T, T)$ of functions, a map $f: T\to T$ has an inverse function if and only if it is bijective. Such a map is also called a *permutation* of $T$. The set of permutations forms a group.

$$
S_n = \text{group of permutations of} ~ \{~1, \cdots, n~\}
$$

#### 2.3 Property
1. *Cancellation* Law
Let $a, b, c$ be elments of a group $G$, If $ab = ac$, then $ba = ca$, then $b = c$