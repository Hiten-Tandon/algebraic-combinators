---
header-includes:
  - \usepackage{cancel}
---
# Orbits, Fixed Points, and Stabilizers

Let $G \subseteq \text{Perm}[U]$
Then 
$$\forall u \in U, G\ u := \left\{\sigma(u) | \sigma \in G\right\}$$
$$\forall \sigma \in G, U^{\sigma} := \left\{u \in U | \sigma(u) = u \right\}$$
$$\forall u \in U, G_u := \left\{\sigma \in G | \sigma(u) = u \right\}$$

## Orbit-Stabilizer Theorem
$\forall G \subset \text{Perm}[U], \ni G$ is a [permutation group](<./Permutation Groups.pdf>)
$$|G| = |Gu| \cdot |G_u|$$

### Proof
$$\forall u \in U$$
$$\forall v \in Gu, \sigma_v \in G \ni \sigma_v(u) = v$$
$$\phi : Gu \times G_u \longrightarrow G$$
$$\phi(v, \sigma_0) := \sigma_v \cdot \sigma_0$$
Claim: 
- $$\forall x, x\prime \in Gu, \tau, \tau\prime \in G_u, \phi(x, \tau) = \phi(x\prime, \tau\prime) \iff x = x\prime, \tau = \tau\prime$$
- $$\forall \sigma \in G, \exists x \in Gu, \tau \in G_u \ni \phi(x, \tau) = \sigma$$
Proof:\
Let, 
  $$x, x\prime \in Gu,$$
  $$\tau, \tau\prime \in G_u$$
  $$\text{s.t. } \phi(x, \tau) = \phi(x\prime, \tau\prime)$$
Then, We know that,
  $$\phi(x, \tau) = \sigma_x\cdot\tau$$
  $$\phi(x\prime, \tau\prime) = \sigma_{x\prime}\cdot\tau\prime$$
  $$\because \phi(x, \tau) = \phi(x\prime, \tau\prime)$$
  $$\implies \phi(x, \tau)(u) = \phi(x\prime, \tau\prime)(u)$$
  $$\implies \sigma_x\cdot\tau(u) = \sigma_{x\prime}\cdot\tau\prime(u)$$
  $$\because \tau, \tau\prime \in G_u$$
  $$\implies \tau(u) = \tau\prime(u) = u$$
  $$\implies \sigma_x(u) = \sigma_{x\prime}(u)$$
  $$\iff \boxed{x = x\prime} \tag{1}$$
  $$\because \sigma_x = \sigma_{x\prime}$$
  $$\implies \cancel{\sigma_x}\cdot\tau = \cancel{\sigma_x}\cdot\tau\prime$$
  $$\iff \boxed{\tau = \tau\prime} \tag{2}$$
  $$\boxed{(1), (2) \implies \phi \text{ is an injective function}}$$

Let,
  $$\sigma \in G,$$
  $$u, v \in U \ni \sigma(u) = v$$
Then, we know that,
  $$\exists \tilde\sigma \in G \ni \sigma\cdot\tilde\sigma = \tilde\sigma\cdot\sigma = \lambda x.x$$
  $$\lambda x.x \in G_u$$
  $$\because \sigma\cdot(\lambda x.x) = \sigma \in G$$
  $$\implies \boxed{\forall \sigma \in G \exists u \in U, \tau \in G_u, \ni \phi(u, \tau) = \sigma} \tag{3}$$

$$\boxed{(1), (2), (3) \implies \phi \text{ is a injective and surjective(bijective) function}}$$
