---
toc: false
header-includes:
  - \usepackage{mathrsfs}
---
# The Pumping Lemma 
Consider
$$L = {0^n 1^n : n \in \mathbb{N}}$$
where $0^n$ means $0$ repeated $n$ times.
Then $L$ can be represented by the generated function
$$L(x) = \sum_{i = 0}^\infty x^{2i} = \frac 1 {1 - x^2}$$

$L$ has a generating function however it isn't a regular language.
This can be proven using the Pumping lemma.

Lemma:
$$\forall L \subseteq \Sigma^* \ni \text{regular}(L)$$
$$\implies \exists p \in \mathbb{P} \ni \forall w \in L, |w| \ge p$$
$$\implies \exists x,y,z \in \Sigma^*, (xyz = w) \wedge (|y| \in \mathbb{P}) \wedge (|xy| \le p) \wedge (\forall n \in \mathbb{N}, xy^nz \in L)$$

Now take the original Language $L$, $\because$ this language can't be represented in the aforementioned way, we can conclude
that it isn't a finite automaton.
Proof:
Let
$$w = xyz \ni w \in L \implies w = 0^n1^n, n \in \mathbb{P}, \ni |xy| \le n \wedge |y| > 0 \wedge x, y, z \in L$$
The only solution to this is $x, z = \emptyset \wedge y = w \because$ if $x \ne \emptyset$, This would imply 
that $x$ is either all $0$s, or $y$ is all $1$s, which both imply that $x \notin L$ and $y \notin L$ respectively.
Which are both contradictions.

HOWEVER this then means that $\nexists p \ne 1 \ni y^p \in L \iff \not\forall p \in P, y^p \in L, \therefore$ the statement is proven
by contradiction.zen-browser/desktop/releases/download/${version}/zen.linux-${arch}.tar.xz


### Proof for the Pumping Lemma
Let

- $L$ be a regular Language over $\Sigma$ character-set,
- recognized by the FSA $M = \left(Q, \Sigma, \delta : Q \times \Sigma \longrightarrow Q, q_0 \in Q, F \subseteq Q\right)$
- Pumping Length $p = |Q_M|$
- $w \in L \ni |w| \ge  p$
- the ordered tuple of states visited to reach $w$, $(q_i)_{0 \le i \le p}$

We know that 
  $$\because \#((q_i)_{0 \le i \le p}) = p + 1$$
  $$\implies \exists i, j \in [p] \ni i \ne j, q_i = q_j \text{(The pigeon hole principle)}$$
  $$\because i \ne j \wedge q_i = q_j$$
  $\implies$ there exists a cycle from $i^{th}$ to $j^{th}$ state in the FSA.\
  $\implies$ You can visit this cycle as many times as you want and the FSA will still recognize the word.\
  $\implies$ If we let $x = (q_k)_{0 \le k \le i}, y = (q_l)_{i < l \le k}, z = (q_m)_{k < m \le n}$\
Then we can always achieve the original structure from the definition of the Pumping Lemma.
$$\blacksquare$$

### Generalization of the pumping lemma
#### Statement
$$\forall L \subseteq \Sigma^* \ni \text{regular}(L)$$
$$\implies \exists p \in \mathbb{P} \ni \forall w \in L, |w| \ge p$$
$$\implies w = xyz \ni |xy| \ge p \wedge |y| > 0 \wedge x, y, z \in L$$
$$\implies \forall u,v \in L \ni uwv \in L, uxy^nzv \in L$$

Proof:
$$uwv \in L$$
$$\iff uxyzv \in L$$
$$\iff ux \in L \wedge zv \in L$$

Let

- $$\alpha = ux$$
- $$\beta = zv$$
$$\implies uxyzv = \alpha y \beta$$
However, we already proved that if $\exists xyz \in L \ni \forall n \in Pxy^nz \exists \in L$
$\blacksquare$
