# Power and sequences of Binomial type

$$\forall R : \text{ Combinatorial species }, \forall \lambda \in \mathbb{N}$$
$$R^{\lambda}(x) = \sum_{n \in \mathbb{N}} \mathcal{r}_n(\lambda)\cdot \frac{x^n}{n!}$$

## Lemma

$$\forall n, \lambda, \mu \in \mathbb{N} \mathcal{r}_n(\lambda + \mu) = \sum_{k = 0}^n {n \choose k} \mathcal{r}_k(\lambda) \cdot \mathcal{r}_{n - k}(\mu)$$
Proof:
$$R^{\lambda + \mu} = R^{\lambda} \circ R^{\mu}$$
Now you can get the lemma trivially by comparing coefficients
