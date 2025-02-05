---
toc: false
---
# The fundamental theorem of finite distributive lattices (Birkhoff's representation theorem)

$$\forall (\Lambda, \le, \vee, \wedge) \ni |\Lambda| < \infty \wedge \forall a, b, c \in \Lambda$$
- $$a \vee (b \wedge c) = (a \vee b) \wedge (a \vee c)$$
- $$a \wedge (b \vee c) = (a \wedge b) \vee (a \wedge c)$$
Theorem:
- $$P_\Lambda := \left\{x \in \Lambda | \forall y \in \Lambda, x \vee y = x\right\}$$
- $$\forall (P, \le), J(P) = \{\{x \in P | x \le y\} | y \in P\}$$
- $$\Lambda \cong J(P_\Lambda)$$
Proof:\
Let $\phi_\Lambda : \Lambda \longrightarrow J(P_\Lambda)$
$$\phi_\Lambda = \lambda x.\left\{y \in P | y \le_\Lambda x\right\}$$
Here, $\phi_\Lambda$ is an order preserving injection.

Lemma: $\forall x \in \Lambda \exists Y \subset \left\{z \in \Lambda | \forall y \in \Lambda, z \le y\right\}, x =  \underset{y \in Y}\bigvee\ y$\
This is trivial, because Lattices are closed under meet($\wedge$) and join($\vee$) operations, and all we're saying is
for all elements of some Lattice, either that element can not be represented using join of two or more elements, or it can't be$\left(x = \underset{y \in \{x\}}\bigvee y\right)$.
Which is a tautology, because it is defined for every element.

Lemma: $\forall x \in \Lambda, \underset{y \in \phi_\Lambda(x)}\bigvee y = x$
