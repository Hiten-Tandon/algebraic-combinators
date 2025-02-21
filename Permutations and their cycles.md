# Permutations and their cycles

$$\mathbb{U} := \left\{X : X\text{ is a set}, |X| < \infty \right\}$$
$$\forall U \in \mathbb{U}$$
$$\text{Perm}[U] := \left\{\sigma : U \rightarrow U | \forall x, z \in U, x \neq z \iff \sigma(x) \neq \sigma(z)\right\}$$

Permutations can be represented by a directed graph $\Gamma_{\sigma} := (U, \sigma)$.
```{.mermaid format=pdf}
graph TD
  u --> v
  v --> w
```

A consequence of this is that every connected component of $\Gamma_{\sigma}$ is a k-cycle $k \in \mathbb{P}$

```{.mermaid format=pdf}
graph LR
  a0 --> a1 --> a2 --> a3 --" .  .  . "--> a0
```

## Cycle structure of $\sigma$

The lengths of the cycles of $\sigma$ written in weakly decreasing order. Integer partition of $|U|$
$(3, 2)$ integer partition of 5 cycle decomposition.

```{.mermaid format=pdf}
graph TD
  u1 --> u3 --> u4 --> u1
  u2 --> u5
```
### Transfer of structure in Permutations.

$$\forall f : U \longrightarrow V \ni \forall x, y \in D_f, x = y \iff f(x) = f(y)$$
$$\sigma \in \text{Perm}[U]$$

Define 

$$f[\sigma](f(u)) := f(v) \iff \sigma(u) = v$$
This is called transfer of Permutations from $U$ to $V$.

```{.mermaid format=pdf}
graph LR
  u1-->u3-->u4-->u1
  u1==f==>v1
  u3==f==>v3
  u4==f==>v4
  v1-->v3-->v4-->v1
  u2-->u5
  u2==f==>v2
  u5==f==>v5
  v2-->v5

  linkStyle default stroke:red;
```

$\sigma \longmapsto f[\sigma]$ is a bijection.

### Unsigned Stirling number of the first kind
$$\forall n, k \in \mathbb{N}$$
$$s(n, k) := \#(\left\{ \sigma \in S_n | \sigma \text{ has }k \text{ cycles}\right\})$$

#### Lemma
$$s(n, k) = \begin{cases}
s(n - 1, k - 1) + (n - 1)\cdot s(n - 1, k) & \text{iff } k \in [1, n - 1]\\
1 & \text{iff } k = n\\
0 & \text{otherwise}
\end{cases}$$

#### Proof
- $s(n, n) = 1$, the proof is trivial, If there are $n$ vertices and every cycle has $n$ vertices
of-course you only have one cycle.
- $s(n, k) \ni k \le 0 \vee k > n = 0$, the proof is again trivial, since no cycle has $0$ vertices,
and $n$ vertices can't make cycles of length greater than $n$, we just get the set as $\emptyset$
which has a definitional cardinality of $0$.
- $s(n, k) \ni k \in [1, n - 1] = s(n - 1, k - 1) + (n - 1)\cdot s(n - 1, k)$

Going from $n$ nodes to $n + 1$ nodes, there are two ways to add a node such that
the number of edges remains number of vertices plus one. We must also add an edge.

However to do so, we can
1. Add the node in a cycle, so the cycle goes from having $y$ nodes to $y + 1$ nodes.
2. Add the node in a cycle with itself, so that the number of cycles goes from $k$ to $k + 1$
3. Point the edge from the new vertex to a vertex in cycle or vice versa (not adding it in a cycle)

However, the 3<sup>rd</sup> way of doing this, leads to the new value no longer being a part of the set $S_{n + 1}$
because, by definition $S_n[X] := \left\{\sigma : X \longrightarrow X | \forall x, y x = y \iff \sigma (x) = \sigma (y) \right\}$
and having 2 incoming edges or two outgoing edges contradicts that.

<!-- TODO: Complete the proof -->

#### Lemma
$$\forall n, \sum_{k=0}^n s(n, k) = n!$$
$$\forall n, \sum_{k = 0}^n s_2(n, k) = B_n$$
