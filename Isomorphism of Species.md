---
header-includes:
  - \usepackage{tikz}
  - \usetikzlibrary {positioning}
---
# Isomorphism of Species

## Definition

Let,
  $F, G$ be two Combinatorial Species,

We say that,

$F \cong G \iff \forall U \in \Omega \exists \phi_U: F[U] \longrightarrow G[U] \ni \phi_U$ is a bijection which respects transport of structure.

$$
\boxed{
  \begin{tikzpicture}[
    -latex,
    auto,
    node distance = 3 cm and 4cm,
    on grid,
    thick,
    state/.style = { 
      circle, 
      top color = white, 
      bottom color = blue!20, 
      draw, 
      blue, 
      text=blue, 
      minimum width = 1 cm
    }
  ]
    \node[state] (n1) {$F[U]$};
    \node[state] (n2) [right = of n1] {$F[V]$};
    \node[state] (n3) [below = of n1] {$G[U]$};
    \node[state] (n4) [below = of n2] {$G[V]$};
    \path (n1) edge [color = blue] node[] {$\sigma$} (n2);
    \path (n1) edge [color = red] node[] {$\phi_U$} (n3);
    \path (n2) edge [color = red] node[] {$\phi_V$} (n4);
    \path (n3) edge [color = blue] node[] {$\sigma$} (n4);
  \end{tikzpicture}
}
$$
**$$\text{Transfer of structure by } \phi_U$$**
More formally speaking, $\forall F, G: \text{ Combinatorial Species, } F \cong G \iff \forall \sigma: U \longrightarrow V \in \Gamma, \phi_V \circ F[\sigma] = G[\sigma] \circ \phi_U$

### Example
$$\mathcal{Inv}_0[U]$$
