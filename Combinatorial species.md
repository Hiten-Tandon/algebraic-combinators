---
header-includes:
  - \usepackage{tikz}
  - \usetikzlibrary {positioning}
  - \usepackage{xcolor}
  - \usepackage{caption}
---
# Combinatorial Species

## Definition
Let

- $$\Omega := \{S \text{ is a Set}: |S| < \infty \}$$
- $$\Gamma := \{\sigma : U \longrightarrow V | U, V \in \Omega, |U| = |V|, \forall x, y \in U, \sigma(x) = \sigma(y) \iff x = y\}$$

It's a rule $F$ which:

- $$\forall U \in \Omega \exists F[U] \in \Omega \text{(Set of F structures on U)}$$
- $$\forall \sigma : U \longrightarrow V \in \Gamma \exists F[\sigma] \in \Gamma, F[\sigma] : F[U] \longrightarrow F[V] \text{(Transport of F structure along } \sigma \text)$$
- $$\forall \sigma : U \longrightarrow V, \tau : V \longrightarrow W \in \Gamma, F[\sigma \circ \tau] = F[\sigma] \circ F[\tau], F[id_U] = id_{F[U]}$$

## Examples
- $\mathcal{G}$: The Species of simple Graphs
  - $\forall U \in \Omega, \mathcal{G}[U]$: A graph with vertex set $U$.
  - $\forall \sigma \in \Gamma, \mathcal{G}[\sigma]$: A graph transformation, where $\sigma$ is applied to all values.

- $\mathcal{S}$: The Species of all Permutations
  - $\mathcal{S}[U] = \left\{\sigma : U \longrightarrow U | \forall x, y \in U, x = y \iff \sigma(x) = \sigma(y)\right\}$
  - $\mathcal{S}[\sigma](\alpha)(\sigma(u)) = \sigma(\alpha(u))$



$$
\boxed{
\begin {tikzpicture}[
  -latex,
  auto,
  node distance = 3 cm and 4cm,
  on grid,
  thick,
  state/.style = { circle, top color =white , bottom color = blue!20, draw, blue, text=blue, minimum width = 1 cm}
]
  \node[state] (n1) {$u_1$};
  \node[state] (n2) [above left = of n1]{$u_2$};
  \node[state] (n3) [above right = of n1]{$u_3$};
  \node[state] (n5) [right = of n3] {$u_5$};
  \node[state] (n4) [below = of n5] {$u_4$};
  \path [bend left = 20] (n1) edge (n2);
  \path [bend left = 20](n2) edge (n3);
  \path [bend left = 20](n3) edge (n1);
  \path [bend left = 15] (n4) edge (n5);
  \path [bend left = 15] (n5) edge (n4);
\end{tikzpicture}
}
$$
**$$\text{Figure: }\alpha$$**

$$
\boxed{
\begin {tikzpicture}[
  -latex,
  auto,
  node distance = 3 cm and 4cm,
  on grid,
  thick,
  state/.style = { circle, top color =white , bottom color = blue!20, draw, blue, text=blue, minimum width = 1 cm}
]
  \node[state] (n1) {$\sigma(u_1)$};
  \node[state] (n2) [above left = of n1]{$\sigma(u_2)$};
  \node[state] (n3) [above right = of n1]{$\sigma(u_3)$};
  \node[state] (n5) [right = of n3] {$\sigma(u_5)$};
  \node[state] (n4) [below = of n5] {$\sigma(u_4)$};
  \path [bend left = 20] (n1) edge (n2);
  \path [bend left = 20] (n2) edge (n3);
  \path [bend left = 20] (n3) edge (n1);
  \path [bend left = 15] (n4) edge (n5);
  \path [bend left = 15] (n5) edge (n4);
\end{tikzpicture}
}
$$
**$$\text{Figure: }\sigma(\alpha)$$**

### Some Standard Species
- $\mathcal{G}$: Simple Graphs
- $\mathcal{G}^0$: Connected Simple Graphs
- $\mathcal{a}$: Trees
- $\mathcal{A}$: Rooted Trees
- $\mathcal{D}$: Directed Graphs
- $\mathcal{Par}$: Set Partitions
- $\mathcal{P}$: Power-set construction
- $\mathcal{End}$: Endo-functions
- $\mathcal{Inv}$: Involutions
- $\mathcal{S}$: Permutations
- $\mathcal{C}$: Species of Cycles
- $\mathcal{L}$: Species of Linear Orders
- $\forall U \in \Omega, E[U] := \{U\}$: Species of Sets
- $\forall U \in \Omega, \varepsilon[U] := U$: Species of set-elements
- $\forall U \in \Omega, X[U] := \begin{cases}\{U\} & \text{iff } |U| = 1 \\ \emptyset & \text{otherwise}\end{cases}$: Species of singleton sets
- $\forall U \in \Omega, 1[U] := \begin{cases}\{U\} &\text{iff } U = \emptyset \\ \emptyset &\text{otherwise}\end{cases}$
- $\forall U \in \Omega, 0[U] := \emptyset$
- $\forall U \in \Omega, E_k(U):= \begin{cases}\{U\} & \text{iff } |U| = k \\ \emptyset & \text{otherwise}\end{cases}$
