---
toc: false
font: "JetBrains Mono NerdFont"
---
# Möbius Function on the set of Ideals

$$\forall A, B \in J(P) \ni A \subset B$$
We know that,
$$\mu_{J(P)}\ A\ B = \mu_{[A, B]}\ \hat0\ \hat1$$

Lemma: 
$$[A, B] \cong J(B / A)$$
Proof:
$$f_{[A, B]} = X \longmapsto X / A$$
$$f_{[A, B]}^{-1} = X \longmapsto X \cup A$$

$$\implies \boxed {\mu_{[A, B]}\ \hat0\ \hat1 = \mu_{J(B / A)}\ \hat0\ \hat1}$$

Then by Weisner's Theorem:
$$\mu_{J(P)}\ \hat0\ \hat1 = - \sum_{\substack{I \ne \hat0 \\ I \cap A = \emptyset}} \mu_{J(P)}(I, \hat1)$$

Theorem:
$$\mu_{J(P)}\ X\ Y =
\begin{cases}
  -1^{|Y/X|} & \text{iff } \forall Z \in Y / X, \left|Z\right| = 1,\\
  0 & \text{otherwise.}
\end{cases}
$$

Case 1 : $\exists x \in X, y \in max(X) \ni x < y$
Take $A = P / \{y\}$, then 
$$X \cap A = \emptyset \implies X \subseteq {y}$$
case I: $X = \emptyset = \hat0$
case II: $X = \{y\}$ which it can't be because then X wouldn't be an Ideal.
$$\implies X = \emptyset$$
$\boxed{\implies \mu_{P(E)}\ \hat0\ \hat1 = 0}$ if X isn't an antichain

Case 2 : $\nexists x \in X, y \in max(X) \ni x < y$
$$\implies J(P) = 2^P$$
$$\implies \mu_{J(P)}\ \hat0\ \hat1 = -1^{|P|}$$
And in case of X and Y 
$$\implies \boxed{\mu_{J(P)}\ X\ Y = -1^{|Y / X|}}$$
$$\blacksquare$$
