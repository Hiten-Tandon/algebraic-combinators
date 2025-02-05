---
toc: false
---

# Distributive Lattices

A Distributive lattice is defined as follows:
$$\forall (\Lambda, \le, \vee, \wedge) \ni \forall \alpha, \beta, \gamma \in \Lambda$$
$$\alpha \wedge (\beta \vee \gamma) = (\alpha \wedge \beta) \vee (\alpha \wedge \gamma),$$
$$\alpha \vee (\beta \wedge \gamma) = (\alpha \vee \beta) \wedge (\alpha \vee \gamma).$$

For example:
- $\forall P, (\Lambda \subseteq 2^P, \subseteq, \cup, \cap)$ is a Distributive lattice. (Distributive laws of sets)
- $(\mathbb{P}, |, \gcd, \text{lcm})$ is also a Distributive lattice.
- $(J(P), \subseteq, \cup, \cap)$ is also a Distributive lattice.

Definitions:
- Join irreducible: $\forall (\Lambda, \le, \vee, \wedge), \forall x \in \Lambda \ni x \ne \hat{0}, \forall y, z \in \Lambda \ni x = y \vee z, (x = y) \vee (x = z)$

Theorem:
$\forall (P, \le), \forall x \in P, I(x)$ is always Join irreducible

Proof:\
Assume, $\exists I(x) = I(y) \cup I(z) \ni x \ne y, x \ne z$\
Case 1: $(x < y) \vee (x < z)$
$$\implies (I(x) \subset I(y)) \vee (I(x) \subset I(z))$$ 
$$\implies I(x) \subset I(y) \cup I(z)$$
$$\implies (x \not< y) \wedge (x \not< z)$$
Case 2: $(z < x)$
$$\implies I(z) \subset I(x)$$
$$\implies I(z) \cup I(y) = I(x) \iff y = x$$
$$\implies z \not< x$$
Case 3 $(y < x)$
$$\implies I(y) \subset I(x)$$
$$\implies I(y) \cup I(z) = I(x) \iff z = x$$
$$\implies y \not< x$$
Case 4 $(z \not< x) \vee (y \not< x)$:
$$\implies (I(z) \Delta I(x) \neq \emptyset) \vee (I(y) \Delta I(x) \neq \emptyset)$$
$$\implies (I(z) \cup I(y))\Delta I(x) \neq \emptyset$$
$$\implies z < x \wedge y < x$$
However, we have already proven that those can't be the case, hence we can say that
$\nexists I(x) = I(y) \cup I(z) \ni x \ne y, x \ne z$
$$\blacksquare$$
