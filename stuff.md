---
toc: false
---
$$\forall x, y \in \mathbb{N}$$
$$\text{add}(x, y) := \begin{cases}
x & \text{iff } y = 0\\
\text{Succ}(\text{add}(x, z)) & \text{iff } y = \text{Succ}(z)
\end{cases}$$
$$\text{mul}(x, y) := \begin{cases}
  0 & \text{iff } x = 0 \vee y = 0\\
  x & \text{iff } y = 1\\
  \text{add}(x, \text{mul}(x, z)) &\text{iff } y = \text{Succ}(z)
\end{cases}
$$
$$\text{power}(x, y) := \begin{cases}
1 & \text{iff } y = 0\\
x & \text{iff } y = 1\\
\text{mul}(x, \text{power}(z)) & \text{iff } y = \text{Succ}(z)
\end{cases}$$
