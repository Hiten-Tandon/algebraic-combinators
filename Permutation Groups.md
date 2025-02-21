# Permutation Groups

$$\forall U: \text{Set} \ni |U| < \infty, \text{Perm}[U] := \left\{\sigma : U \longrightarrow U | \forall x, y \in U, \sigma(x) = \sigma(y) \iff x = y \right\}$$

## Lemmas
$$\exists \text{id}_U \in \text{Perm}[U] \ni \forall x \in U, \text{id}_U(x) = x$$
$$\forall \sigma, \tau \in \text{Perm}[U], \sigma \cdot \tau \in \text{Perm}[U]$$
$$\forall \sigma \in \text{Perm}[U] \exists \tilde\sigma \in \text{Perm}[U] \ni \sigma\cdot\tilde\sigma = \tilde\sigma\cdot\sigma = \text{id}_U$$
$$\forall \sigma, \tau, \mu \in \text{Perm}[U] \sigma\cdot(\tau\cdot\mu) = (\sigma\cdot\tau)\cdot\mu=\sigma\cdot\tau\cdot\mu$$
$$\forall \sigma \in \text{Perm}[U], \sigma\cdot \text{id}_U = \text{id}_U\cdot\sigma = \sigma$$
$$\forall \sigma, \tau, \tau\prime \in \text{Perm}[U], \sigma\cdot\tau = \sigma\cdot\tau\prime \iff \tau = \tau\prime$$
$$\forall \sigma, \sigma\prime, \tau \in \text{Perm}[U], \sigma\cdot\tau = \sigma\prime\cdot\tau \iff \sigma = \sigma\prime$$

## Permutation Group
### Definition
$$G \subseteq \text{Perm}[U] \ni$$
- $$G \neq \emptyset$$
- $$\forall \sigma, \tau \in G, \sigma\cdot\tau \in G$$
- $$\forall \sigma \in G, \exists \tilde\sigma \in G \ni \sigma\cdot\tilde\sigma = \tilde\sigma\cdot\sigma = \text{id}_U$$

$$\forall \sigma \in \text{Perm}[U], k \in \mathbb{N}, \sigma^k := \begin{cases}
id_U & \text{iff } k = 0,\\
\sigma\cdot(\sigma^{k-1}) & \text{iff } k > 0
\end{cases}$$
$$\forall \sigma \in \text{Perm}[U]\text{ord}{\sigma} := \text{min}(\{t \ni \sigma^t = \text{id}_U, t \ne 0\})$$
### Lemma
- $$G \ni \text{id}_U$$
- $$\forall \sigma \in Perm[U], \exists k < l \ni \sigma^k = \sigma^l$$
  $$\implies \text{id}_U = \sigma^{l - k}$$
- $$\forall \sigma \in Perm[U] \{\sigma^k | k \in \mathbb{N}, k < \text{ord}(\sigma)\} \in \{G\}$$
- $$\forall \sigma \in Perm[U], \text{ord}\sigma = \text{lcm}(\lambda_i)_{i \le n}$$
#### Proof ($\forall G, G \ni \text{id}_U$)
$$\because G \neq \emptyset, |G| \ge 1$$
$$\implies \exists \sigma \in \text{Perm}[U] \ni \sigma \in G$$
$$\because \sigma \in G \iff \tilde\sigma \in G$$
$$\implies \{\sigma, \tilde\sigma\} \subseteq G$$
$$\because \forall \sigma, \tau \in G, \sigma\cdot\tau \in G$$
$$\implies \sigma\cdot\tilde\sigma \in G$$
$$\implies \text{id}_U \in G$$
$$\blacksquare$$

### Graph Automorphism Group

$$\forall V,E \Gamma := (V, E) \ni E \subseteq V \times V$$
$$\text{Aut}(\Gamma) := \left\{\sigma \in \text{Perm}[V] | \forall \{x, y\} \in E \iff \{\sigma(x), \sigma(y)\} \in E  \right\}$$

##### Benzene Group
$$\text{Aut}(\Gamma) \subset S_6$$
This group has 
- 12 elements
- 6 rotations
- 6 reflections

```{.graphviz format=pdf}
graph benzene {
  label = "Benzene Group";
  labelloc="t";
  fontsize=16;
  layout=neato;
  overlap=true;
  splines=false;

  C1 [label="C", pos="1,0!"];
  C2 [label="C", pos="0.5,0.87!"];
  C3 [label="C", pos="-0.5,0.87!"];
  C4 [label="C", pos="-1,0!"];
  C5 [label="C", pos="-0.5,-0.87!"];
  C6 [label="C", pos="0.5,-0.87!"];

  C1 -- C2;
  C2 -- C3;
  C3 -- C4;
  C4 -- C5;
  C5 -- C6;
  C6 -- C1;

  C1 -- C4 [style=dashed, color=gray, constraint=false];
  C2 -- C5 [style=dashed, color=gray, constraint=false];
  C3 -- C6 [style=dashed, color=gray, constraint=false];

  M1 [shape=point, label="", pos="0.75,0.435!", width=0.1];
  M2 [shape=point, label="", pos="0,0.87!", width=0.1];
  M3 [shape=point, label="", pos="-0.75,0.435!", width=0.1];
  M4 [shape=point, label="", pos="-0.75,-0.435!", width=0.1];
  M5 [shape=point, label="", pos="0,-0.87!", width=0.1];
  M6 [shape=point, label="", pos="0.75,-0.435!", width=0.1];

  // Draw symmetry lines (dashed, here colored blue) connecting opposite midpoints.
  M1 -- M4 [style=dashed, color=blue, constraint=false];
  M2 -- M5 [style=dashed, color=blue, constraint=false];
  M3 -- M6 [style=dashed, color=blue, constraint=false];
}
```


