---
header-includes:
  - \usepackage{amsmath}
---

# LGV Lemma

## Some background theory

$$\forall M_{n\times n} := (m_{i\cdot j})_{i, j = 1}^n$$
$$\text{Inv}(\sigma) := \{(i, j) | 1 \le i < j \le n, \sigma(i) > \sigma(j)\}$$
$$\text{sgn}(\sigma) := (-1)^{|\text{Inv}(\sigma)|}$$
$$\det(M) := \sum_{\sigma \in S[n]} \text{sgn}(\sigma) \cdot \prod_{i = 1}^n m_{\sigma(i)\cdot i}$$

### Properties of sgn
- $\forall \sigma, \tau \ni (\forall \sigma(i) > \sigma(j), \tau(j) > \tau(i)), \text{sgn}(\tau) = -\text{sgn}(\sigma)$

## Motivation

### Suci Prastara

- Suggested by Pingala (200 BCE), is a method to compute Binomial coefficients

$$A := (a_{i \cdot j}), a_{i \cdot j} = \begin{cases} 1 \text{ if } i = 0, \sum_{k = 1}^{j} a_{(i - 1)\cdot k} \text{ otherwise} \end{cases} = {i + j \choose i}$$

$$
A := 
\begin{pmatrix}
  1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 & \dots \\
  1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & \dots \\
  1 & 3 & 6 & 10 & 15 & 21 & 28 & 36 & \dots \\
  1 & 4 & 10 & 20 & 35 & 56 & 84 & 120 & \dots \\
  1 & 5 & 15 & 35 & 70 & 126 & 210 & 336 & \dots \\
  1 & 6 & 21 & 56 & 126 & 252 & 462 & 792 & \dots \\
  \vdots & \vdots & \vdots & \vdots & \vdots & \vdots & \vdots & \vdots & \ddots
\end{pmatrix}
$$

Every minor of this matrix is positive.

### Halayudha method (aka Meru Prastara, aka Pascal's triangle)

$$
B :=
\begin{pmatrix}
  1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & \dots \\
  1 & 1 & 0 & 0 & 0 & 0 & 0 & 0 & \dots \\
  1 & 2 & 1 & 0 & 0 & 0 & 0 & 0 & \dots \\
  1 & 3 & 3 & 1 & 0 & 0 & 0 & 0 & \dots \\
  1 & 4 & 6 & 4 & 1 & 0 & 0 & 0 & \dots \\
  1 & 5 & 10 & 10 & 5 & 1 & 0 & 0 & \dots \\
  1 & 6 & 15 & 20 & 15 & 6 & 1 & 0 & \dots \\
  \vdots & \vdots & \vdots & \vdots & \vdots & \vdots & \vdots & \vdots & \ddots
\end{pmatrix}
$$


LGV Lemma can be used to show that all minors of the above to matricies are positive.
