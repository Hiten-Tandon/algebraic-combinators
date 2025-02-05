---
toc: false
header-includes: 
  - \usepackage{stmaryrd}
---
# Formal Power series

 $$\forall (F, \oplus, \odot, 0, 1) \ni \forall x \in F \exists \tilde{x} \ni x \oplus \tilde{x} = 0\wedge\forall y \in F / \{0\} \exists \hat{y} \ni y \odot \hat{y} = 1$$

Let

$$F\llbracket x\rrbracket := \left\{\left.\sum_{i=0}^\infty a_i \odot x^i \right | \forall i, a_i \in F \right\}$$

## Definitions

$$\forall f, g \in F\llbracket x \rrbracket$$
$$f \oplus g := \sum_{i = 0}^\infty (a_{g \cdot i} \oplus a_{f \cdot i})\odot x^i$$
$$f - g := f \oplus \tilde{g}$$
$$f \odot g := \sum_{i = 0}^\infty\sum_{j+k =i}(a_{g \cdot j} \odot a_{f \cdot k}) \odot x^i$$
$$\text{val} := \lambda f.\min \{n | a_n \neq 0\}$$
$$\forall f \in F\llbracket x \rrbracket, |f| := \begin{cases}
2^{-{\text{val}\ f}} & \text{iff } f \neq 0\\
0 & \text{o/w}
\end{cases}$$
$$d := \lambda f.\lambda g.|f - g|$$

## Theorem
$\forall (F, \oplus, \odot, 0, 1) \ni \forall x \in F \exists \tilde{x} \ni, x \oplus \tilde{x} = 0 \wedge \forall y \in F \exists \hat{y} \ni y \odot \hat{y} = 1, F\llbracket x\rrbracket$ is 
1. a commutative unital RING and,
2. a Metric Space

## Lemmas

- $\forall f \in F\llbracket x \rrbracket, f \oplus \sum\limits_{i = 0}^\infty 0\odot x^i = f$
- $\forall f \in F \llbracket x \rrbracket, f \odot \sum\limits_{i = 0}^\infty a_i \odot x^i (\ni a_0 = 1 \wedge a_{i > 0} = 0) = f$
- $\forall f, g\in F\llbracket x \rrbracket, f\oplus g = g \oplus f$
- $\forall f, g \in F\llbracket x \rrbracket f \odot g = g \odot f$
- $\forall f, \in F\llbracket x \rrbracket \exists \tilde{f} \in F\llbracket x\rrbracket \ni f \oplus \tilde{f} = \sum\limits_{i = 0}^{\infty}0\odot x^i$
- $\forall f, g \in F\llbracket x \rrbracket, d\ f\ g = d\ g\ f$
- $\forall f, g \in F\llbracket x \rrbracket \ni f = g \iff d\ f\ g = 0$
- $\forall f, g \in F\llbracket x \rrbracket d\ f\ g \in \{x \in \mathbb{Q}^+ | 0 \le x \le 1\}$
- $\forall f, g, h \in F\llbracket x \rrbracket \ni f \neq g \neq h, d\ f\ g \leq \max (d\ f\ h) (d\ g\ h) \leq d\ f\ h + d\ g\ h$


## Proofs

1.
$$\forall f \in F\llbracket x \rrbracket, f \oplus \sum\limits_{i = 0}^\infty 0\odot x^i = f$$
By definition of $f \oplus g$
$$f \oplus \sum_{i = 0}^\infty0\odot x^i = \sum_{i = 0}^\infty(a_{f \cdot i} + 0) \odot x^i$$
Since, 0 is the addition identity of F, We can simplify the expression to
$$\boxed{\sum_{i = 0}^\infty a_{f\cdot i}\odot x^i}$$
Which is just the definition of $f$
$$\blacksquare$$

2. $$\forall f \in F \llbracket x \rrbracket, f \odot \sum\limits_{i = 0}^\infty a_i \odot x^i (\ni a_0 = 1 \wedge a_{i > 0} = 0) = f$$
By the definition of $f \odot g$,
$$f \odot \sum_{i = 0}^\infty a_i\odot x^i (\ni a_0 = 1 \wedge a_{i > 0} = 0) = \sum_{i = 0}^\infty \sum_{j + k = i}(a_{f\cdot j} \odot a_k)\odot x^i (\ni a_0 = 1, a_{k > 1} = 0)$$
$\because$ 0 is the product irreducible element of F, $\implies \forall k > 0, a_{f \cdot j} \odot a_k = 0$
$\because$ 0 is the additive identity element of F, $\implies \sum\limits_{j + k = i} (a_{f\cdot j} \odot a_k) = a_{f \cdot i}$
$$\implies \boxed{\sum_{i = 0}^\infty \sum_{j + k = i}(a_{f\cdot j} \odot a_k)\odot x^i (\ni a_0 = 1, a_{k > 1} = 0) = \sum_{i = 0}^\infty a_{f\cdot i} \odot x^i}$$
Which is just the definition of f
$$\blacksquare$$
3. $$\forall f, g\in F\llbracket x \rrbracket, f \oplus g = g \oplus f$$
Simplifying using the definition of $f \oplus g$
LHS:
$$f \oplus g = \sum_{i = 0}^\infty (a_{f\cdot i} \oplus a_{g\cdot i}) \odot x^i$$
RHS:
$$g \oplus f = \sum_{i = 0}^\infty (a_{g\cdot i} \oplus a_{f\cdot i})\odot x^i$$
We know that $\forall a, b \in F a \oplus b = b \oplus a$
$$\implies \forall i, a_{g\cdot i} \oplus a_{f\cdot i} = a_{f\cdot i} \oplus a_{g\cdot i}$$
Hence we can just change the terms in the summation to be equal. Since two summations are equal, if all of their co-efficients are equal, this proves the lemma.
$$\blacksquare$$
4. $$\forall f, g\in F\llbracket x \rrbracket, f\odot g = g\odot f$$
Simplifying by defintion
LHS:
$$f\odot g = \sum_{i = 0}^\infty\sum_{j + k = i}(a_{f\cdot j} \odot a_{g\cdot k})x^i$$
RHS:
$$g\odot f = \sum_{i = 0}^\infty\sum_{j + k = i} (a_{g\cdot j}\odot a_{f\cdot k})x^i$$
$\because j, k \in \mathbb{N} \implies \{j | j + k = i\} = \{k | j + k = i\}, \wedge \forall x, y, z \in F, x \oplus (y \oplus z) = (x \oplus y) \oplus z$ 
$$\implies LHS = RHS$$
$$\blacksquare$$
5. $$\forall f \in F\llbracket x \rrbracket \exists \tilde{f} \in F\llbracket x\rrbracket \ni f \oplus \tilde{f} = \sum_{i = 0}^{\infty}0\odot x^i$$
Simplifying by deffinition
$$f \oplus \tilde{f} = \sum_{i = 0}^\infty (a_{f\cdot i} \oplus a_{\tilde{f}\cdot i}) \odot x^i$$
To prove that,
$$\forall i, a_{f\cdot i} \exists a_{\tilde{f}\cdot i} \ni a_{f\cdot i} \oplus a_{\tilde{f}\cdot i} = 0$$
Remember,
$$\forall i, a_{f\cdot i}, a_{\tilde{f}\cdot i} \in F \implies a_{\tilde{f}\cdot i} = \widetilde{a_{f\cdot i}}$$
$$\blacksquare$$
6. $$\forall f, g \in F\llbracket x \rrbracket, d\ f\ g = d\ g\ f$$
Case 1 $(f = g)$:
$$d\ f\ g = d\ g\ f = 0$$
so the lemma holds
Case 2 $(f \neq g)$:
LHS:
$$d\ f\ g = |f - g| = 2^{-\text{val}(f - g)} = 2^{-\min\{n | a_{f\cdot n} - a_{g\cdot n} \neq 0\}}$$
RHS:
$$d\ g\ f = |g - f| = 2^{-\text{val}(g - f)} = 2^{-\min\{n | a_{g\cdot n} - a_{f\cdot n} \neq 0\}}$$
$\because \forall a, b \in \mathbb{Z}, a - b \neq 0 \iff b - a \neq 0$ This proves the lemma.
$$\blacksquare$$
7. $$d\ f\ g = 0 \iff f = g$$
$$d\ f\ g = |f - g| = |f \oplus \tilde{g}| = 0 \iff f \oplus \tilde{g} = 0$$
$$\implies \tilde{g} = \tilde{f}$$
$$\implies g = f$$
$$\blacksquare$$
8. $$\forall f, g \in F\llbracket x \rrbracket, d\ f\ g \in \{x \in \mathbb{Q}^+ | 0 \le x \le 1\}$$
This is trivial, since it can just be proven by simplifying the definition of d.

9. $$\forall f, g, h, \in F\llbracket x \rrbracket d\ f\ g \leq \max (d\ f\ h) (d\ g\ h) \leq d\ f\ h + d\ g\ h$$
Proving first inequality\
LHS:
$$d\ f\ g = |f - g| = 2^{-\text{val}(f - g)} = 2^{-\min\{n | a_{f\cdot n} - a_{g\cdot n} \neq 0\}}$$
RHS:
$$\max (d\ f\ h) (d\ g\ h) = \max (2^{-(\text{val } f - h)})(2^{-(\text{val } g - h)}) = \max 2^{-\min\{n | a_{f\cdot n} - a_{h\cdot n} \neq 0\}}\ 2^{-\min\{n | a_{g\cdot n} - a_{h\cdot n} \neq 0\}}$$
$$2^{\max\ (-\min\{n | a_{f\cdot n} - a_{h\cdot n} \neq 0\})\ (- \min\{n | a_{g\cdot n} - a_{h\cdot n} \neq 0\})}$$
Taking $\log_2$ on both sides, we can rewrite the inequality to be 
$$-\min\{n | a_{f\cdot n} - a_{g\cdot n} \neq 0\} \le \max\{-\min\{n | a_{f\cdot n} - a_{h\cdot n} \neq 0\}, -\min\{n | a_{g\cdot n} - a_{h\cdot n} \neq 0\}\}$$





















