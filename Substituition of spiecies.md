---
header-includes:
  - \usepackage {tikz}
  - \usetikzlibrary {positioning}
---
# Substitution of species

## Definition

  $$F, G: \text{Combinatorial structure} \ni G[\emptyset] = \emptyset$$
$$\implies F \circ G = \sum_{\pi \in Par[U]} F[\pi] \times \prod{p \in \pi} G[p]$$
$$ = \left\{\left(\pi, \phi, \gamma\right) : \text{Par}[U] \times F[\pi] \times (\gamma_p)_{p \in \pi} \right\}$$
$$Z_{F \circ G}(x_i)_{i \in \mathbb{N}} = Z_F(Z_G(x_{k\cdot i})_{i \in \mathbb{N}})_{k \in \mathbb{N}}$$
$$\widetilde{F \circ G}(x) = Z_F(\tilde{G}(x^i))_{i \in \mathbb{N}}$$
$$F \circ G(x) = F(G(x))$$
**$$\text{F}\circ\text{G}$$**
![](F_circle_G.svg)
This is also called an $F$-assembly of $G$-structures.

## Example

$$\mathcal{End}[U] \subseteq \{F: U \longrightarrow U\}$$
$$\mathcal{End}[U] \cong \mathcal{S \circ A}$$
![](End_=_S_circ_A.png)


$$\left|\mathcal{End}\left[\left[n\right]\right]\right| = n^n$$
$$\implies \left|\mathcal{S\circ A}\left[\left[n\right]\right]\right| = n^n$$
$$\mathcal{End}(x) = \sum_{n \in \mathbb{N}} \frac{n^n\cdot x^n}{n!}$$
$$\mathcal{S\circ A}(x) = \mathcal{S(A}(x)) = \frac{1} {1 - \mathcal{A}(x)}$$
$$\mathcal{End \cong S \circ A \implies End}(x) = \mathcal{S \circ A}(x)$$
$$\implies \sum_{n \in \mathbb{N}} \frac{n^n\cdot x^n}{n!} = \frac{1}{1 - \mathcal{A}(x)}$$
$$\implies \boxed{\mathcal{A}(x) = 1 - \left(\sum_{n \in \mathbb{N}} \frac{n^n \cdot x^n}{n!}\right)^{-1}}$$

