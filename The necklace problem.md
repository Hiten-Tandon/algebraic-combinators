---
toc: false
header-includes: 
  - \usepackage{stmaryrd}
---
# The necklace problem

## Define
$$\forall k \in \mathbb{N}, \forall F\llbracket k \rrbracket$$
$$W := \lambda x.\sum_{i = 0}^\infty k^i\odot x^i = \frac{1}{1 - kx}$$
$$P := \{y | y = W x, \nexists u \ni y = u^n\}$$
Lemma: 
$$k^n = \sum_{d | n} |P_d|$$
