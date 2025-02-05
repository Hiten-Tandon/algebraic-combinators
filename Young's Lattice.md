---
toc: false
---
# Young's Lattice

## Definitions
$$\forall x \in \mathbb{P}$$
$$\Lambda_x = \left\{(\lambda_i)_{i \in [n]} \left| n < \infty \wedge \forall i, \lambda_i \in \mathbb{P} \wedge \forall i, \lambda_i \ge \lambda_{i + 1} \wedge \sum_{i \le n} \lambda_i = x\right.\right\}$$

## Ferrer's diagraph of $\lambda$

$$\forall x \in \mathbb{P}, \forall \lambda \in \Lambda_x$$
$$Y\ \lambda := \left\{(i,\ j) | 1 \le i \le l, 1 \le j \le \lambda_i\right\}$$

The above set can be represented using a 2D array of dots/boxes
such that each succeeding row has less (or equal) elements than the preceding row

### Partial order on the union of all $\Lambda_x$
$$\mathbb{Y} = \bigcup_{x \in \mathbb{P}} \Lambda_x$$
then,
$$\forall \lambda, \mu \in \mathbb{Y}, \mu \subseteq \lambda, \iff |\mu| \le |\lambda| \wedge, \forall i \in \left[\left|\mu\right|\right] \mu_i \le \lambda_i$$
$$\implies \forall \lambda, \mu \in \mathbb{Y}, \mu \subseteq \lambda \iff Y\ \mu \subseteq Y\ \lambda$$

$$\implies (\mathbb{Y}, \subseteq) \longleftrightarrow (\left\{Y\ \rho | \rho \in \mathbb{Y}\right\}, \subseteq)$$

$$\forall \lambda, \mu \in \mathbb{Y} \ni |\lambda| \le \mu$$
$$\lambda \wedge \mu := \mu \vee \lambda := (min(\lambda_i, \mu_i))_{i \in [|\lambda|]}$$
$$\lambda \vee \mu := \mu \vee \lambda := (max(\lambda_i, \mu_i))_{i \in [|\mu|]} \ni \forall i > |\lambda|, \lambda_i = 0$$

Lemma: 
$$\forall \lambda, \mu \in \mathbb{Y}, \lambda \vee \mu \in \mathbb{Y}, \lambda \wedge \mu \in \mathbb{Y}$$
