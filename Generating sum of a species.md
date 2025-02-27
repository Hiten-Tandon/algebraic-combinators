---
header-includes:
  - \usepackage{cancel}
---
# Generating sum of a species

$$\forall F: \text{species}, U, V \in \Omega, \ni \exists \sigma : U \longrightarrow V \in \Gamma$$
$$|F[U]| = |F[V]| (\because F[\sigma] \text{ is bijective.})$$
$$\implies \forall U \ni |U| = n, |F[U]| = |F\left[\left[n\right]\right]|$$
$$f_n := F\left[\left[n\right]\right]$$
$$\boxed{F(x) := \sum_{n \in \mathbb{N}} f_n\cdot \frac{x^n}{n!}}$$

### Examples
- $$\forall U \in \Omega, \mathcal{L}[U], |\mathcal{L}[U]| = |U|!$$
  - $$\implies \mathcal{L}(x) = \sum_{n \in \mathbb{N}} \cancel{n!}\cdot\frac{x^n}{\cancel{n!}} = \frac 1 {1 - x}$$

- $$\mathcal{S}[U]$$
  - $$\mathcal{S}(x) = \sum_{n \in \mathbb{N}} \cancel{n!}\cdot\frac{x^n}{\cancel{n!}} = \frac 1 {1 + x}$$

- $$\forall U \in \Omega, |\mathcal{C}[U]| = (n - 1)!$$
  - $$\implies \mathcal{C}(x) = \sum_{n \in \mathbb{N}} \cancel{(n - 1)!} \cdot \frac{x^n}{\substack{\cancel{n!} \\ n}} = \sum_{n \in \mathbb{N}} \frac{x^n}n = \log \left|\frac 1 {1 - x}\right|$$

- $$\forall U \in \Omega, |\mathcal{D}[U]| = 2^{n^2}$$
  - $$\implies \mathcal{D}(x) = \sum_{n \in \mathbb{N}} 2^{n^2} \cdot \frac{x^n}{n!}$$

- $$\forall U \in \Omega, |\mathcal{G}[U]| = 2^{n\choose{2}}$$
  - $$\implies \mathcal{G}(x) = \sum_{n \in \mathbb{N}} 2^{n\choose2} \frac{x^n}{n!}$$

- $$\forall U \in \Omega, |\mathcal{P}[U]| = 2^n$$
  - $$\implies \mathcal{P}(x) = \sum_{n \in \mathbb{N}} \frac{(2 \cdot x)^n}{n!} = \exp(2\cdot x)$$

- $$\forall U \in \Omega, |\varepsilon[U]| = |U|$$
  - $$\implies \varepsilon(x) = \sum_{n \in \mathbb{N}} \cancel{n} \cdot \frac{x^n}{\cancel n \cdot (n - 1)!} = x \cdot \exp(x)$$

- $$\forall U \in \Omega, |X[U]| = \begin{cases}1 & \text{iff } n = 1 \\ 0 & \text{otherwise} \end{cases}$$
  - $$\implies X(x) = x$$

- $$\forall U \in \Omega, |1[U]| = \begin{cases} 1 & \text{iff } n = 0 \\ 0 & \text{otherwise} \end{cases}$$
  - $$\implies 1(x) = 1$$

- $$\forall U \in \Omega, |E[U]| = 1$$
  - $$\implies E(x) = \sum_{n \in \mathbb{N}} \frac{x^n}{n!} = \exp(x)$$

- $$\forall U \in \Omega, \forall k \in \mathbb{N}, |E_k[U]| = \begin{cases} 1 & \text{iff } n = k \\ 0 & \text{otherwise} \end{cases}$$
  - $$\implies E_k(x) = \frac{x^k}{k!}$$

- $$\forall U \in \Omega, |0(U)| = 0$$
  - $$\implies 0(x) = 0$$
