---
toc: false
---

# Super Catalan or Schröder numbers

## Problem statement

In how many ways can a string of $n$ identical symbols be bracketed?
Here x is a single character string and ++ refers to concatenation of two strings.
Example: xxxx
Can be bracketed as (x(xx)(xx))

## Solution

Let $I x$ be an inductive type defined as following.
$$I x := (x \in \Sigma^*) | (I \vee I)$$
Then we can represent the answer to the question as the following
$$S := \lambda n.\left|\left\{\sigma \in I x : |\sigma| = n \right\}\right|$$
This set is isomorphic to a set of all possible trees with n leaf nodes, such that
each node has a minimum of 2 children nodes if not zero.

| $n$ |                                                              $S\ n$                                                              | $\#(S n)$ |
| :-: | :------------------------------------------------------------------------------------------------------------------------------: | :-------: |
|  1  |                                                             $\{x\}$                                                              |     1     |
|  2  |                                                            $\{(xx)\}$                                                            |     1     |
|  3  |                                                  $\{(xxx), (x(xx)), ((xx)x)\}$                                                   |     3     |
|  4  | $$\{(xxxx), (x(xxx)), ((xxx)x), ((xx)(xx)), (x(x(xx))), ((x(xx))x),$$ $$(x((xx)x)), (((xx)x)x), (xx(xx)), (x(xx)x), ((xx)xx)\}$$ |    11     |

$$S = \mathfrak{X} + Seq_{\ge}(S)$$
$$\implies S(x) = x + \frac{S(x)^2}{1 - S(x)}$$
$$\implies (S(x) - x)(1 - S(x)) - S(x)^2 = 0$$
$$\implies S(x) - S(x)^2 - x + x\cdot S(x) - S(x)^2 = 0$$
$$\implies 2\cdot S(x)^2 - (x + 1)\cdot S(x) + x = 0$$
$$\implies S(x) = \frac{(x + 1) \pm ((x + 1)^2 - 4\cdot 2 \cdot x)^{0.5}}{4}$$
$$\implies S(x) = \frac{(x + 1) \pm (x^2 + 2\cdot x + 1 - 8 \cdot x)^{0.5}}{4}$$
$$\implies S(x) = \frac{(x + 1) \pm (x^2 - 6\cdot x + 1)^{0.5}}{4}$$
$\because$ the $0^\text{th}$ term of the generating function must be $0$ (Definition)
$$\boxed{S(x) = \frac{(x + 1) - (x^2 - 6\cdot x + 1)^{0.5}}{4}}$$
