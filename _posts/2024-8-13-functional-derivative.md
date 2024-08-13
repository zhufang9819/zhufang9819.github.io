---
title: Notes on Functional Derivatives
categories: [Math]
tags: [analysis]
last_modified_at: 2024-08-13
---

# Notes on Functional Derivatives
In this document, we discuss the derivation of functional derivatives for a real-valued function. The focus is on how to handle perturbations in the function and derive the corresponding operator that approximates these changes. We also provide detailed steps on how to apply the divergence theorem to certain terms in the derivation.
<!--more-->

Given a real-valued function $\rho(\bm{r})$ and $\phi(\bm{r})$ defined on the space $(\Omega, \| \cdot \|_p)$, where $\Omega \subseteq \mathbb{R}^{n}$, $\bm{r} \in \Omega$, and both $\rho$ and $\phi$ vanish on the boundary $\partial \Omega$ (or satisfy periodic boundary conditions), we can define the following functional $F(\rho)$:

$$
F(\rho) = \int_{\Omega} f \left( \bm{r}, \rho({\bm{r}}),  \delta\rho({\bm{r}}), \nabla \rho({\bm{r}}), \Delta \rho(\bm{r}) \right) \, d \bm{r} \in \mathbb{R}.
$$

Before deriving the functional derivative of $F$, we first consider the effect of a local perturbation $\phi$ on $F(\rho)$ by analyzing the difference $F(\rho + \phi) - F(\rho)$. As $\| \phi \|_p \to 0$, we wish for $F(\rho + \phi) - F(\rho)$ to be approximated by a certain linear operator $\mathcal{A}(\rho)$ acting on $\phi$, denoted by $\mathcal{A}(\rho; \phi)$, i.e.,

$$
F(\rho + \phi )  - F(\rho) = \mathcal{A}(\rho; \phi) + o (\| \phi \|_p).
$$

We can construct the action of the linear operator $\mathcal{A}(\rho)$ on $\phi$ using the $L_2$ norm on $\Omega$, expressed as:

$$
\mathcal{A}(\rho; \phi) = \int_{\Omega} \mathcal{A}(\rho)  \phi(\bm{r}) \, d \bm{r}.
$$

It is evident that $\mathcal{A}(\rho; \phi)$ is linear in $\phi$, meaning that for $\lambda, \mu \in \mathbb{R}$ and functions $\phi_1, \phi_2$, we have:

$$
\mathcal{A}(\rho; \lambda \phi_1 + \mu \phi_2 ) = \lambda \mathcal{A}(\rho;\phi_1)  + \mu \mathcal{A}(\rho;\phi_2).
$$

To derive $\mathcal{A}(\rho)$, let $\phi = \epsilon \phi$. Substituting this into the previous approximation yields:

$$
F(\rho + \epsilon \phi )  - F(\rho) = \mathcal{A}(\rho; \epsilon \phi) + o (\| \epsilon \phi \|_p).
$$

Given the linearity of the $L_p$ norm and $\mathcal{A}(\rho; \phi)$, we get:

$$
\begin{aligned}
F(\rho + \epsilon \phi )  - F(\rho) & = \epsilon \mathcal{A}(\rho; \phi) +  o (| \epsilon| \|  \phi \|_p) \\
& = \epsilon \mathcal{A}(\rho; \phi) +  o (| \epsilon| ).
\end{aligned}
$$

Dividing both sides by $\epsilon$ and taking the limit as $\epsilon \to 0$ gives:

$$
\begin{aligned}
\lim_{\epsilon \to 0} \frac{F(\rho + \epsilon \phi )  - F(\rho)}{\epsilon} & = \lim_{\epsilon \to 0}  \left(\mathcal{A}(\rho; \phi) +  o (1)\right) \\
& = \mathcal{A}(\rho; \phi).
\end{aligned}
$$

Combining this with the earlier expression for $\mathcal{A}(\rho; \phi)$ yields:

$$
\int_{\Omega} \mathcal{A}(\rho)  \phi(\bm{r}) \, d \bm{r} = \lim_{\epsilon \to 0} \frac{F(\rho + \epsilon \phi )  - F(\rho)}{\epsilon}.
$$

This defines the operator $\mathcal{A}(\rho)$, and to make it consistent with calculus, we can define the functional derivative as $\delta F/ \delta \rho = \mathcal{A}(\rho)$. Thus, we have:

$$
\int_{\Omega} \frac{\delta F}{\delta \rho}  \phi(\bm{r}) \, d \bm{r} = \lim_{\epsilon \to 0} \frac{F(\rho + \epsilon \phi )  - F(\rho)}{\epsilon}.
$$

Next, we demonstrate how to use this to calculate $\delta F / \delta \rho$. According to the definition, we have:

$$
\begin{aligned}
\lim_{\epsilon \to 0} \frac{F(\rho + \epsilon \phi )  - F(\rho)}{\epsilon} & = \left[ \frac{d}{d \epsilon} \int_{\Omega} f(\bm{r}, \rho + \epsilon \phi, \nabla \rho + \epsilon \nabla \phi, \Delta \rho + \epsilon \Delta \phi ) \, d \bm{r}\right]_{\epsilon = 0} \\ 
& = \int_{\Omega} \frac{\partial f}{\partial \rho} \phi + \underbrace{\frac{\partial f}{\partial \nabla \rho} \cdot \nabla\phi}_{\text{I}}+ \underbrace{\frac{\partial f}{\partial \Delta \rho} \Delta \phi }_{\text{II}}\, d \bm{r}.
\end{aligned}
$$

We can apply the divergence theorem to terms I and II. First, applying the divergence theorem to term I:

$$
\begin{aligned}
\int_\Omega \frac{\partial f}{\partial \nabla \rho} \cdot \nabla\phi \, d \bm{r} & = \int_\Omega \nabla \cdot \left( \frac{\partial f}{\partial \nabla \rho } \phi \right) - \left( \nabla \cdot \frac{\partial f}{\partial \nabla \rho }\right) \phi \, d \bm{r}  \\
& = \cancel{\int_\Omega \nabla \cdot \left( \frac{\partial f}{\partial \nabla \rho } \phi \right) \, d \bm{r}} - \int_\Omega \left( \nabla \cdot \frac{\partial f}{\partial \nabla \rho }\right) \phi \, d \bm{r} \\ 
& = - \int_\Omega \left( \nabla \cdot \frac{\partial f}{\partial \nabla \rho }\right) \phi \, d \bm{r}.
\end{aligned}
$$

The crossed-out term equals zero, which can be derived using the divergence theorem combined with the boundary conditions. Now, applying the divergence theorem to term II:

$$
\begin{aligned}
\int_\Omega \frac{\partial f}{\partial \Delta \rho} \Delta \phi \, d \bm{r}& = \int_\Omega \nabla \cdot \left( \frac{\partial f}{\partial \Delta \rho } \nabla \phi \right) - \left( \nabla  \frac{\partial f}{\partial \Delta \rho }\right) \cdot \nabla \phi \, d \bm{r}  \\
& = \cancel{\int_\Omega \nabla \cdot \left( \frac{\partial f}{\partial \Delta \rho } \nabla \phi \right) - \nabla \cdot \left( \nabla \frac{\partial f}{\partial \Delta \rho}\phi \right) }+ \nabla \cdot \left( \nabla  \frac{\partial f}{\partial \Delta \rho }\right)  \phi \, d \bm{r}  \\
& =  \int_{\Omega} \nabla \cdot \left( \nabla  \frac{\partial f}{\partial \Delta \rho }\right)  \phi \, d \bm{r}.
\end{aligned}
$$

Combining these with the earlier expressions, we obtain:

$$
\begin{aligned}
\lim_{\epsilon \to 0} \frac{F(\rho + \epsilon \phi )  - F(\rho)}{\epsilon} & = \left[ \frac{d}{d \epsilon} \int_{\Omega} f(\bm{r}, \rho + \epsilon \phi, \nabla \rho + \epsilon \nabla \phi, \Delta \rho + \epsilon \Delta \phi ) \, d \mathbf{r}\right]_{\epsilon = 0} \\ 
& = \int_{\Omega} \frac{\partial f}{\partial \rho} \phi - \left( \nabla \cdot \frac{\partial f}{\partial \nabla \rho }\right) \phi  + \nabla \cdot \left( \nabla  \frac{\partial f}{\partial \Delta \rho }\right)  \phi \, d \bm{r} \\
& = \int_{\Omega} \left(\frac{\partial f}{\partial \rho} - \nabla \cdot \frac{\partial f}{\partial \nabla \rho } + \Delta \frac{\partial f}{\partial \Delta \rho} \right) \phi \, d \bm{r}.
\end{aligned}
$$

Finally, from the definition of the functional derivative, we have:

$$
\frac{\delta F}{\delta \rho} = \frac{\partial f}{\partial \rho} - \nabla \cdot \frac{\partial f}{\partial \nabla \rho } + \Delta \frac{\partial f}{\partial \Delta \rho}.
$$

A more general discussion on this topic can be found on the Wikipedia page [Functional derivative](https://en.wikipedia.org/wiki/Functional_derivative).

