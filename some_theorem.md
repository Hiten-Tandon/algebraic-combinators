---
toc: false
---
$$\forall (R, \oplus, \odot, 0, 1) \ni \forall a \in R \exists \tilde{a} \ni a \oplus \tilde{a} = 0,$$
$$\forall (P, \le),$$
Definitions: 
$$\forall x \in P, I\ x = \left\{y \in P | y \le x\right\}$$
$$M_P := \left\{f \colon P \rightarrow R \right\} $$
$$A_P := \left\{ f \colon P \rightarrow P \rightarrow R | \forall x, y \in P, f\ x\ y \ne 0 \iff x \le y \right\}$$
Assuming, $\left|I\ x\right| < \infty$
$$\forall f, g \in A_P, f * g = \lambda x.\lambda y. \sum_{z = x}^{y} (f\ x\ z) \odot (g\ z\ y)$$
$$\forall f \in A_P, \forall g \in M_P, g * f = \lambda x. \sum_{y \in P}^{x} (f\ y\ x) \odot (g\ y)$$
Lemma:
$$ \forall f, g \in A_P, \forall \xi \in M_P, \xi * \left(f * g\right) = \left(\xi * f\right) * g$$
Proof: 
$$\xi * (f * g) = \lambda x.\sum_{y \in P}^x (f * g\ y\ x) \odot (\xi\ y)$$
$$= \lambda x.\sum_{y \in P}^x\left(\sum_{z = y}^x \left(f\ y\ z\right) \odot \left(g\ z\ x \right) \right) \odot \left(\xi\ y \right) $$
By the distributive property of multiplication on $R$
$$= \lambda x.\sum_{y \in P}^x\sum_{z = y}^x \left(f\ y\ z\right) \odot \left(g\ z\ x \right) \odot \left(\xi\ y \right) \tag{i}$$
Similarly,
$$\left(\xi * f\right) * g = \lambda x.\sum_{y \in P}^x \left(g\ y\ x\right) \odot \left(\xi * f\ y\right)$$
$$= \lambda x.\sum_{y \in P}^x(g\ y\ x) \odot \left(\sum_{z \in P}^y (f\ z\ y) \odot (\xi\ z) \right) $$
By the distributive property of multiplication on $R$
$$= \lambda x.\sum_{y \in P}^x \sum_{z \in P}^y(g\ y\ x) \odot  (f\ z\ y) \odot (\xi\ z) \tag{ii}$$
To show that (i) = (ii)
Let:
$$\forall x \in P,$$
$$\daleth_x := \left\{\left<\alpha, \beta\right> \in I\ x \times I\ x | \alpha \le \beta\right\}$$
$$\beth_x := \left\{\left<\alpha, \beta\right> \in I\ x \times I\ x | \beta \le \alpha\right\}$$
$$\implies \beth_x = \left\{\left<\beta, \alpha\right> | \left<\alpha, \beta\right> \in \daleth_x\right\}$$

Then, (i) can be re-written as:
$$\lambda x.\sum_{\left<\alpha, \beta\right> \in \daleth_x} (f\ \alpha\ x) \odot (g\ \beta\ x) \odot (\xi\ \alpha)$$
Similarly (ii) can be re-written as:
$$\lambda x.\sum_{\left<\alpha, \beta\right> \in \beth_x} (f\ \beta\ x) \odot (g\ \alpha\ x) \odot (\xi\ \beta)$$

However, $\because, \beth_x = \left\{\left<\beta, \alpha\right> | \left<\alpha, \beta\right> \in \daleth_x\right\}$
$$
\implies 
\sum_{\left<\alpha, \beta\right> \in \beth_x} (f\ \beta\ x) \odot (g\ \alpha\ x) \odot (\xi\ \beta) = \sum_{\left<\beta, \alpha\right> \in \daleth_x} (f\ \beta\ x) \odot (g\ \alpha\ x) \odot (\xi\ \beta)$$
$$
\boxed{
  \sum_{\left<\beta, \alpha\right> \in \daleth_x} (f\ \beta\ x) \odot (g\ \alpha\ x) \odot (\xi\ \beta) =
  \sum_{\left<\alpha, \beta\right> \in \daleth_x} (f\ \alpha\ x) \odot (g\ \beta\ x) \odot (\xi\ \alpha)
}
$$
$$\blacksquare$$
