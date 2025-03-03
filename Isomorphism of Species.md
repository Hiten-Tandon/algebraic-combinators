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
    \path (n1) edge [color = blue] node[] {$F[\sigma]$} (n2);
    \path (n1) edge [color = red] node[] {$\phi_U$} (n3);
    \path (n2) edge [color = red] node[] {$\phi_V$} (n4);
    \path (n3) edge [color = blue] node[] {$G[\sigma]$} (n4);
  \end{tikzpicture}
}
$$
**$$\text{Transfer of structure by } \phi_U$$**
More formally speaking, $\forall F, G: \text{ Combinatorial Species, } F \cong G \iff \forall \sigma: U \longrightarrow V \in \Gamma, \phi_V \circ F[\sigma] = G[\sigma] \circ \phi_U$

### Example
$$\mathcal{Inv}_0[U] := \left\{\sigma \in \mathcal{S}(U) \left| \forall u \in U, \sigma^2(u) = u, \sigma(u) \ne u\right.\right\}$$

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
      bottom color = purple!20, 
      draw, 
      blue, 
      text=purple, 
      minimum width = 1 cm
    }
  ]
  \node[state] (n1) {$1$};
  \node[state] [below = of n1](n2) {$2$};
  \node[state] [right = of n1](n3) {$3$};
  \node[state] [below = of n3] (n4) {$4$};
  \path (n1) edge [bend left = 20] (n2);
  \path (n2) edge [bend left = 20] (n1);
  \path (n3) edge [bend left = 20] (n4);
  \path (n4) edge [bend left = 20] (n3);
\end{tikzpicture}                
}
$$

**$$\text{Fixed point free involution of 4 nodes}$$**

$$M_2[U] := \text{Perfect matchings on the complete graph of U}$$
$$
\boxed{
\begin{tikzpicture}[
    auto,
    node distance = 3 cm and 4cm,
    on grid,
    thick,
    state/.style = { 
      circle, 
      top color = white, 
      bottom color = purple!20, 
      draw, 
      blue, 
      text=purple, 
      minimum width = 1 cm
    }
  ]
  \node[state] (n1) {$1$};
  \node[state] [below = of n1](n2) {$2$};
  \node[state] [right = of n1](n3) {$3$};
  \node[state] [below = of n3] (n4) {$4$};
  \path (n1) edge [color = red] (n2);
  \path (n3) edge [color = red] (n4);
  \path (n1) edge (n4);
  \path (n3) edge (n1);
  \path (n2) edge (n3);
  \path (n4) edge (n2);
\end{tikzpicture}                
}
$$


Define: 
$$\forall s \in \mathcal{Inv}_0[U], \phi_U(s) = (u, s(u))$$

## Theorem

$$\forall F, G: \text{ Combinatorial Species, } F \cong G \implies Z_F = Z_B$$
