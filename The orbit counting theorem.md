# The Orbit counting theorem

$$G \backslash U = \{Gu | u \in U\}$$

## Lemma $\forall u, v \in U, Gu = Gv \vee Gu \cap Gv = \emptyset$
### Proof
$G \subseteq \text{Perm}[U] \ni G$ is a [Permutation Group](<Permutation Groups.md>)
$$Gu = \{\sigma(u) | \sigma \in G\}, Gv = \{\sigma(v) | \sigma \in G\}$$
<!--TODO: Complete the proof -->

### Example 1
$$G = \left<\sigma\right> = \{\sigma^i\}_{0 \le i < \text{ord}(\sigma)}$$
$$Gu = \left<\sigma\right>u = \{\sigma^i(u)\}_{0 \le i < \text{ord}(\sigma)}$$

### Example 2
$$U_{n,k} := \{f: [n] \xmapsto{C} [k]\}$$
Let,
$$\sigma \in \text{Perm}[U_{n,k}]$$
$$\sigma(c)(i) := \begin{cases}
c(i - 1) & \text{iff } i \in [2, n]\\
c(n) & \text{iff } i = 1
\end{cases}$$

## Orbit counting Theorem

$$\left|G \backslash U\right| = \frac 1 a \sum_{\sigma \in G} U^{\sigma}$$
