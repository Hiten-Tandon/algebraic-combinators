# Statement of the LGV Lemma

$$S: \text{A Set of vertices}$$
$$\mathcal{v}: S \times S \longrightarrow \mathbb{R} \text{Weight functions}$$
$$\left\{A_i\right\}_{i \le n \le \infty} \subseteq S$$
$$\left\{B_i\right\}_{i \le n \le \infty} \subseteq S$$

A path $\omega$ from $x$ to $y$ is defined as a set of nodes in order 
such that every pair of 2 nodes is connected by an edge and the first node is $x$ and the last node is $y$.

More formally
$$\omega_{x \rightarrow y} := \left<x, ..., y\right>$$

Weight of path $\omega_{x \rightarrow y}$ is defined as $\mathcal{v}(\omega) := \prod_{i \in [|\omega|]} \mathcal{v}(s_{i - 1}, s_i)$

Consider a Matrix 
$$M := (m_{ij})_{i, j \in [n]}), n \in \mathbb{N}$$
$$\forall i, j \in [n], m_{ij} = \sum_{\omega_{A_i\rightarrow B_i}} \mathcal{v}(\omega)$$
