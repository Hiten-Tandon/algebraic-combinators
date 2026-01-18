# Symmetric polynomials

$$\forall n \in \mathbb{P}$$
$$\forall (R, 0, 1, \oplus, \odot) \ni \forall x \exists \tilde{x} \ni x \oplus \tilde{x} = 0$$
$$R[x_i]_{i = 1}^n = \{\text{polynomials with coefficients in } R \text{ and variables } x_1 \cdots x_n\}$$

## Monomials 

$$n \in \mathbb{P}, \forall i, \alpha_i \in \mathbb{Z}^+, \prod_{i \le n} x_i^{\alpha_i}$$
$$\alpha := \left<a_i\right>_{i = 1}^n$$
$$\alpha \in \left(\mathbb{Z}^+\right)^n$$

FACT:

Let, 
$$f(x_1, \ldots, x_n) \in R[x_i]_{i = 1}^n$$
Then, $f$ can be rewritten as 
$$\sum_{\alpha \in \mathbb{Z}_+^n}c_{\alpha}\cdot x^\alpha \ni \forall \alpha, c_{\alpha} \in R$$

## Definition

A polynomial $f(x_1, \ldots, x_n) \in R[x_i]_{i = 1}^n$ is called symmetric if:
$$\forall X, Y := \left<x_i\right>_{\substack{i \in X\\ X \in \mathcal{S}([n])}}, fX = fY$$

For example:\
Let $f$ be a polynomial of 2 variables. Then $f$ is symmetric if: $f(x, y) = f(y, x)$
- $\forall a, b \in \mathbb{P}, c_1, c_2 \in R f(x, y) = c_1(x^ay^b + y^bx^a) + c_2xy$

Let $f$ be a polynomial of 3 variables. Then $f$ is symmetric if: $f(x, y, z) = f(x, z, y) = f(y, x, z) = f(y, z, x) = f(z, x, y) = f(z, y, x)$

### Proposition

Let $f(X) = \sum_{\alpha \in \mathbb{Z}_+^n}c_{\alpha}X^{\alpha}$ be a polynomial
then $f$ is symmetric $\iff \forall \lambda, \gamma \in S(\alpha), c_{\lambda} = c_{\gamma}$

