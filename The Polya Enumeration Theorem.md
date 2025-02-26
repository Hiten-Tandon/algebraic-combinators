# The Polya Enumeration Theorem

## Problem Statement

$$\forall U : \text{ is a Set } \ni |U| < \infty$$
$$\forall G \subseteq \text{Perm}[U]$$
$$\forall k \in \mathbb{P}$$
$$\forall c, c\prime : U \longrightarrow [k] \ni \exists \sigma \in G c\prime(\sigma(u \in U)) = c \iff c \sim_G c\prime$$
$$C_k(U) := \{f: U \longrightarrow [k]\}$$
$$G \backslash C_k(U) := \left\{\left. \left\{\tau \in C_k(U)| \tau \sim_G \sigma \right\} \right| \sigma \in C_k(U) \right\}$$

## Example

$$G = \left<\sigma\right> = \{\sigma^i\}_{0 \le i < \text{ord}(\sigma)}$$

```{.mermaid format=pdf}
graph LR
  1((1)) --- 2((2)) --- 3((3)) --- 4((...)) --- k((n - 1)) --- n((n)) --- 1((1))
```

Given:
$$c \in C_k(U)$$
Let
$$\alpha_i := \#\{u \in U | c(u) = i\}$$
$$\alpha_c := (\alpha_i)_{1 \le i \le k} \in \mathbb{N}^k$$
$$\sum_{i=1}^k \alpha_i = |U|$$
$\alpha_c$ is called the shape of the coloring $c$.
$$c \sim_G c\prime \iff \alpha_c = \alpha_{c\prime}$$
$$\forall k < \infty \in \mathbb{N}, \forall \alpha_k \in \mathbb{N}^k$$
$$C_{\alpha}(U) := \{c \in C_k(U)| \alpha_c = \alpha\}$$

#### Problem

Determine the number of G-equivalent classes of colourings of $U$ with shape $\alpha$.\\

#### Solution

1. Power sum symmetric Polynomials
   Let $f: S^k \longrightarrow U \ni \forall \omega \in \text{Perm}[S], \omega(S^k) \longmapsto u \in U$
   For example $p_m(x_i)_{1 \le i \le k} = \sum_{i=1}^k x_i^m$ can be a possible value of $f$.
