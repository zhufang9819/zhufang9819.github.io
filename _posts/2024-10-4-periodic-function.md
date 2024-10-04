---
title: Notes on Periodic Condition and Divergence Theorem
categories: [Math]
tags: [analysis]
last_modified_at: 2024-10-04

---

In the study of partial differential equations (PDEs), periodic boundary conditions are frequently employed to model systems with repeating structures or to simplify the analysis of infinite domains. When a function is defined to be periodic on a given domain, not only the function itself but also its derivatives often inherit certain periodic properties. This notes explores the implications of periodic boundary conditions on the gradient and Laplacian of a function defined on a rectangular domain. We demonstrate that if a function is periodic, its gradient and Laplacian are also periodic, which is critical in the analysis of PDEs with periodic solutions. 

<!--more-->


Consider a function $f(x, y)$ defined on the domain $\Omega$. We assume $f$ is periodic, satisfying:

$$
f(x, y) = f(x+T_1, y), \quad f(x, y) = f(x, y + T_2),
$$

where $T_1$ and $T_2$ represent the periodicity in the $x$- and $y$-directions, respectively. We claim the following:

**Proposition 1.** *If $f(x, y)$ is periodic, then $\nabla f(x, y)$ is also periodic.*

**Proof.** By the definition of the gradient, we have:

$$
\nabla f(x, y) = (\partial_x f, \partial_y f),
$$

where $\partial_\star f$ denotes the partial derivative of $f$ with respect to $\star$. For the $x$-
direction, we calculate $\partial_x f(a, b)$ as follows:

$$
\partial_x f(a, b) = \lim_{h \to 0} \frac{f(a+h, b) - f(a ,b)}{ h}.
$$

Since $f$ is periodic, the equation above can be rewritten as:

$$
\begin{aligned}
\partial_x f(a, b) &= \lim_{h \to 0} \frac{f(a+h, b) - f(a ,b)}{ h} \\
&= \lim_{h \to 0} \frac{f(a+h + T_1, b) - f(a+T_1, b)}{ h} \\
&= \partial_x f(a+T_1, b).
\end{aligned}
$$

Similarly, we have:

$$
\partial_y f(a, b) = \partial_y f(a, b + T_2).
$$

Thus, $\nabla f(x, y) = (\partial_x f, \partial_y f)$ is periodic. $\blacksquare$

By induction, we extend this result to higher-order derivatives:

**Corollary 1.** *If $f(x, y)$ is periodic, then $\Delta f(x, y)$ is also periodic.*

In problems involving partial differential equations, we often assume a solution $u(x, y)$ satisfies periodic boundary conditions on the boundary $\partial \Omega$ of $\Omega = [0, T_1] \times [0, 
T_2]$. We can then derive:

$$
\begin{aligned}
\int_{\Omega} \nabla \cdot (\nabla u(x, y)) \, d \mathbf{x} &= \int_{\partial \Omega} \nabla u(x, y) \cdot \mathbf{n} \, d S = 0, \\
\int_{\partial \Omega} \nabla u(x, y) \cdot \mathbf{n} \, d S &= 0,
\end{aligned}
$$

where the first equation follows directly from the divergence theorem. The second equation can be demonstrated using domain decomposition and Proposition 1. The proof is as follows:

**Proof.** We first partition the boundary $\partial \Omega$ into four segments, $\partial \Omega_1, \partial \Omega_2, \partial \Omega_3, \partial \Omega_4$, as depicted in the figure below:

<img src="/assets/images/regular_domain.png" alt="image-20241004152544545" style="zoom: 80%;" />

We have:

$$
\begin{aligned}
\int_{\partial \Omega} \nabla u(x, y) \cdot \mathbf{n} \, d S &= \int_{\partial \Omega_1} \nabla u(x, y) \cdot \mathbf{n} \, d S + \int_{\partial \Omega_2} \nabla u(x, y) \cdot \mathbf{n} \, d S \\
&\quad + \int_{\partial \Omega_3} \nabla u(x, y) \cdot \mathbf{n} \, d S + \int_{\partial \Omega_4} \nabla u(x, y) \cdot \mathbf{n} \, d S.
\end{aligned} \tag{1}
$$

Using Proposition 1 and the periodic boundary conditions on $u(x, y)$, we obtain:

$$
\nabla u(x, y)\big|_{\partial \Omega_1} = \nabla u(x, y)\big|_{\partial \Omega_2}, \quad \nabla u(x, y)\big|_{\partial \Omega_3} = \nabla u(x, y)\big|_{\partial \Omega_4}. \tag{2}
$$

Moreover, since $\Omega$ is a rectangular domain, we have:

$$
\mathbf{n}\big|_{\partial \Omega_1} = -\mathbf{n}\big|_{\partial \Omega_2}, \quad \mathbf{n}\big|_{\partial \Omega_3} = -\mathbf{n}\big|_{\partial \Omega_4}. \tag{3}
$$

Combining equations (1), (2), and (3), we conclude:

$$
\int_{\partial \Omega} \nabla u(x, y) \cdot \mathbf{n} \, d S = 0,
$$

which is the desired result. $\blacksquare$
