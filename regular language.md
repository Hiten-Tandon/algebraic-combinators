---
toc: false
header-includes:
  - \usepackage{mathrsfs}
---

# Regular language or Regular Expressions

Let,
$A$ be a finite alphabet with $k$ elements.
$$W_A := \{(a_i)_{i \le n} | n \in \mathbb{N}, a_i \in A\}$$

## Definition

A formal language in $A$ is a subset $\mathscr{L} \subset W$

Example:

- The set of all C programs that can be compiled using a C compiler are a formal
  language in the character set of ASCII.
- $A = \{H, T\}$, $\mathfrak{T} = \{(a_i)_{(i \le n)} | n \in \mathbb{N},
a_i \in A, \#(i \ni a_i = H) = \#(j \ni a_j = T)\}$

## RegExs

A RegEx is the smallest formal language $R$ (on character set of $A$) with the following:

- $$\varepsilon \in R$$
- $$A \subset R$$
- $$\forall u, v \in R, u | v \in R$$
- $$\forall u, v \in R, u \cdot b \in R$$
- $$\forall u \in R, u^* \in R$$

### Matching

We'll show matching with the symbol $\dag$
$$\forall w \in W, r \in R$$
$$\dag : W \longrightarrow R \longrightarrow \{\text{false}, \text{true}\}$$

$$
\begin{array}{ll}
w \dag r &:=\\
   &|\ (w = \varepsilon) \wedge (r = \varepsilon)\\
   &|\ (w = r) \wedge w \in A \wedge r \in A\\
   &|\ (w \dag u \vee w \dag v) \wedge (r = u|v)\\
   &|\ (w = w_1w_2 \wedge w_1 \dag u \wedge w_2 \dag v) \wedge (r = u \cdot v)\\
   &|\ (w = (w_i)_{i \le n \in \mathbb{N}} \wedge \forall i, w_i \dag u)
\wedge (r = u^*)
\end{array}
$$

Implementation example: ripgrep on Linux and Unix\

Example:

- $\text{colo}(\text{u}|\varepsilon)\text{r}$ matches color and colour $((x|\varepsilon)$ is commonly written as $x?)$
- $(0|1)^*0$ matches all binary strings which represent even numbers.

## Definition

A language $\mathfrak{L}_u$ is called $S$-regular if it consists of all the words that match a given regular expression $u$.
$$\mathfrak{L}_u := \{w \in W | w \dag u\}$$

$$L_u := \sum_{w \in \mathfrak{L}_u} x^{|w|}$$
$$\implies L_\varepsilon(x) = 1, $$
$$\forall a \in R, L_a(x) = |x|$$
$$\forall u, v \in R \ni , L_{u|v}(x) = L_u(x) + L_v(x)$$
$$\forall u, v \in R, L_{u\cdot v}(x) = L_u(x) \cdot L_v(x)$$
$$L_{u^*}(x) = \frac 1 {1 - L_u(x)}$$
$$$$
