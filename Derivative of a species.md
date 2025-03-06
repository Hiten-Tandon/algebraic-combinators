---
header-includes:
  - \usepackage{tikz}
  - \usetikzlibrary {positioning}
  - \usepackage{ifthen}
  - \usepackage{graphicx}
  - \usepackage{array}
---

# Derivatives of a species

## Definition

Let $F$ be a species of structures, then we define it's derivative $F^{\prime} = \frac{d}{dx}F := F[U^+] \ni U^+ = U \cup \{*_U\}$

$$\forall, \sigma: U \longrightarrow V, \sigma^+ : U^+ \longrightarrow V^+ := \begin{cases}\sigma(u) & \text{iff } u \in U\\ *_v & \text{otherwise.}\end{cases}$$

## Example 1

$$\mathcal{C}^{\prime} \cong \mathcal{L}$$

### Proof 1

Let $\mathcal{C}_n$ be species of cycles with $n$ nodes,\
then, for $\mathcal{C^{\prime}_n}$ we just "point out" a node from the $\mathcal{C}_n$\
$\because$ it doesn't really matter which node you "point out" from the cycle $(\because, [n] = \left<n, 1, ..., n - 1\right> )$\
We consider the resulting set as just a singleton set consisting of only the Cycle with $n$ nodes,\
Which as you can see visually in the following figure is isomorphic to a Linear Ordering with $n - 1$ nodes.

$$
\boxed{
\boxed{
\begin{tikzpicture}[
  -latex,
  every
  node/.style={
    draw,
    circle,
    top color=purple!80,
    bottom color=blue!80
  },
  edge/.style = {
    draw = green,
    thick,
  }
  ]
   \def \n {20}
   \def \radius {3cm}
   \node[top color = red!100, bottom color = red!100] (node1) at ({0}:\radius) {};
   \foreach \i in {2,...,\n} {
       \node (node\i) at ({360/\n * (\i - 1)}:\radius) {};
   }
   \node[draw = none, top color=white, bottom color = white, font=\Large\bfseries] (center) at (0,0) {$\mathcal{C^{\prime}}_{\n}$};
   \foreach \i in {2,...,\numexpr\n-1\relax} {
       \pgfmathtruncatemacro{\j}{mod(\i,\n)+1}
       \path (node\j) edge[color = green!100, thick] (node\i);
   }
  \path (node1) edge[color = red!100, thick, dotted] (node\n);
  \path (node2) edge[color = red!100, thick, dotted] (node1);
\end{tikzpicture}
}
\mathrel{\raisebox{19ex}{\scalebox{1.5}{\Huge =}}}
\boxed{
\begin{tikzpicture}[
  -latex,
  every
  node/.style={
    draw,
    circle,
    top color=purple!80,
    bottom color=blue!80
  },
  edge/.style = {
    draw = green,
    thick,
  }
  ]
   \def \n {20}
   \def \radius {3cm}
   \node[top color = red!100, bottom color = red!100] (node2) at ({18}:\radius) {};
   \foreach \i in {1,3,4,...,\n} {
       \node (node\i) at ({360/\n * (\i - 1)}:\radius) {};
   }
   \node[draw = none, top color=white, bottom color = white, font=\Large\bfseries] (center) at (0,0) {$\mathcal{C^{\prime}}_{\n}$};
   \foreach \i in {3,...,\n} {
       \pgfmathtruncatemacro{\j}{mod(\i,\n)+1}
       \path (node\j) edge[color = green!100, thick] (node\i);
   }
  \path (node3) edge[color = red!100, thick, dotted] (node2);
  \path (node2) edge[color = red!100, thick, dotted] (node1);
\end{tikzpicture}
}
}
$$

$$\scalebox{2}{\rotatebox{270}{\Huge $\cong$}}$$

$$
\boxed{
\begin{tikzpicture}[
  -latex,
  every
  node/.style={
    draw,
    circle,
    top color=purple!80,
    bottom color=blue!80
  },
  edge/.style = {
    draw = green,
    thick,
  }
  ]
   \def \n {20}
   \def \radius {3cm}
   \foreach \i in {2,...,\n} {
       \node (node\i) at ({360/\n * (\i - 1)}:\radius) {};
   }
   \node[draw = none, top color=white, bottom color = white, font=\Large\bfseries] (center) at (0,0) {$\mathcal{L}_{(\n - 1)}$};
   \foreach \i in {2,...,\numexpr\n-1\relax} {
       \pgfmathtruncatemacro{\j}{mod(\i,\n)+1}
       \path (node\j) edge[color = green!100, thick] (node\i);
   }
\end{tikzpicture}
}
$$

## Example 2

$$\left(X^n\right)^{\prime} \cong n \cdot X^{n - 1}$$

### Proof 2

$$X^n \cong \mathcal{L}_n$$
This assertion is trivial because $X$ is the species of singletons, and if you create
an ordered tuple of $n$ singletons, that is the same as having a linear order with $n$ nodes.
$\implies$ $\mathcal{L}_n^\prime \cong n \cdot \mathcal{L}_{n - 1}$ Following is the visual proof of this.

$$
\def \n {6}
\boxed{
\foreach \cnt in {1, ..., \n} {\boxed{
\begin{tikzpicture}[
-latex,
  every
  node/.style={
    draw,
    circle,
    top color=purple!80,
    bottom color=blue!80
  }]
  \node[draw=none, top color = white, bottom color = white] (node0) {$\mathcal{L_{\n}^{\prime}}$};
  \foreach \i in {1,...,\n} {
    \pgfmathtruncatemacro{\prev}{\i-1}
    \ifthenelse {\equal{\i}{\cnt}}
      {\node[top color = red, bottom color = red] (node\i) [above = of node\prev] {}}
      {\node (node\i) [above=of node\prev] { }};
  }
  \foreach \i in {2, ..., \n} {
    \pgfmathtruncatemacro{\prev}{\i-1}
    \ifthenelse {\(\equal{\i}{\cnt}\) \OR \(\equal{\prev}{\cnt}\)}
      {\path (node\prev) edge [thick, dotted, color = red] (node\i)}
      {\path (node\prev) edge [thick, color = green!100] (node\i)};
  }
\end{tikzpicture}
}
\ifthenelse {\not \equal{\cnt}{\n}}{\mathrel{\raisebox{100pt}{\scalebox{2}{$,$}}}} {}
}
}
\raisebox{110pt}{\scalebox{2}{\Huge $\cong$}}
\raisebox{20pt}{
\def \n {5}
\pgfmathtruncatemacro{\x}{\n + 1}
\boxed{
\raisebox{90pt}{\scalebox{3}{$\x \cdot$}}
\boxed{
\begin{tikzpicture}[
-latex,
  every
  node/.style={
    draw,
    circle,
    top color=purple!80,
    bottom color=blue!80
  }]
  \node[draw=none, top color = white, bottom color = white] (node0) {$\mathcal{L_{\n}}$};
  \foreach \i in {1,...,\n} {
    \pgfmathtruncatemacro{\prev}{\i-1}
    \node (node\i) [above=of node\prev] { };
  }
  \foreach \i in {2, ..., \n} {
    \pgfmathtruncatemacro{\prev}{\i-1}
    \path (node\prev) edge [thick, color = green!100] (node\i);
  }
\end{tikzpicture}
}}}
$$

Note that in a Linear order, the selected node **does** change the original order,
because unlike in case of cycles, rotations of a Linear order are not the same.
Hence we end with a set of $n$ distinct structures in the set. HOWEVER all of these
structures are isomorphic to $\mathcal{L}_{n - 1}$ so, after performing the transformation,
we're left with $n$ structures of type $\mathcal{L}_{n - 1}$ which are equal.

## Example 3

$$\mathcal{L}^{\prime} = L^2$$

## Example 4

$$\text{Par_p} = E \circ \text{Par}$$
