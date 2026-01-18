# Elementary and complete symmetric polynomials

## Elementary symmetric polynomials

For some arbitrarily large $n$, fix variables $[x_i]_{i = 1}^n$

Then an Elementary symmetric polynomial of degree $k$ is defined as 
$$e_{\left< k, n\right>} := \begin{cases}\sum_{\lambda \in \Lambda}\prod_{i = 1}^n x_{\lambda_i} \left(\Lambda := \{\left<\alpha_i\right>_{i = 1}^k \left| \forall i, j \le k, i < j \iff \alpha_i < \alpha_j \right.\}\right) & \text{iff } k \le n\\ 0 & \text{otherwise} \end{cases}$$

### Lemma 
$$\prod_{i = 1}^n (1 + t \cdot x_i) = \sum_{d = 0}^n t^d \cdot e_{\left< d, n\right>}$$

## Complete or Homogeneous symmetric polynomials

$$h_d := \sum_{\alpha: \sum{\alpha_i} = d} x ^{\alpha} = \sum_{\lambda \in \mathcal{P}(d, n)} m_{\lambda}(x)$$
$$h_0 := 1$$

### Lemma 

$$\prod_{i = 1}^n \left(\frac {1} {1 - t\cdot x_i}\right) = \sum_{d \ge 0} t^d \cdot h_d(x)$$
