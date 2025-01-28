# Ideals in a Poset
Let $(P, \le)$ be a Partially ordered set. Then an Ideal is any subset of P such that
for any element x in I, it also has all the elements of P which are less than x.

Defintion:
$$\forall x \in P, I(x) = \left\{y \in P | y \le x\right\}$$
$$J(P) = \left\{I(x)|x \in P\right\}$$

Let 
$$\{X_i\}_{i \in \beth} \subseteq J(P)$$
then,\
Lemma:
$$\bigcup_{i \in \beth} X_i \subseteq J(P)$$
$$\bigcap_{i \in \beth} X_i \subseteq J(P)$$

Proof (Induction):\
Base Case $(\{X_i\}_{i \in \beth} = \left\{\phi\right\})$:
  $$\bigcup_{i \in \beth} X_i = \phi$$
  $$\bigcup_{i \in \beth} X_i = \phi$$
$$\because \left\{\phi\right\} \subseteq J(P)$$
We can say base case holds

Inductive Case:\
Let $\{X_i\}_{i \in \beth} \subset J(P)$ for which this lemma holds\
and, let $\{Y_i\}_{i \in \daleth} \subseteq J(P) \ni \beth \subset \daleth, \{X_i\}_{i \in \beth} \subset \{Y_i\}_{i \in \daleth}$
<!-- TODO: Complete the proof -->

Lemma:
$(J(P), \subseteq)$ is a lattice

Defintion:
$$\forall S \subseteq P, I(S) = \bigcap_{\substack{I \in J(P) \\ S \subseteq I}} I$$
$$\forall (S, \le), max(S) = \left\{y \in S | x \nexists S \ni y < x \right\}$$

Lemma: 
$\forall (S, \le) \ni 0 < \left|S\right| < \infty, max(S)$ is an anti-chain
Proof by Induction:\

Base case $(S = \{x\})$:
$$\because S = \{x\} \implies max(S) = S$$
Since S is an anti-chain Base case holds.

Inductive Case $\left(S = X \cup \{\alpha\}\right) \ni max(X)$ is an anti-chain\
case 1: 
  $$\exists x \in max(X) \ni \alpha < x \implies max(S) = max(X)$$ 
  $$\implies max(S)\text{ is an anti-chain, because max(X) is an anti-chain (inductive hypothesis)}$$
case 2: 
  $$\nexists x \in max(X) \ni \alpha < x \implies max(S) = max(X) \cup \{\alpha\}$$ 
  $$\implies max(S)\text{ is an anti-chain, there is no element of that which is related to } \alpha$$
