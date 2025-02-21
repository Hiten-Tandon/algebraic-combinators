---
toc: false
---
# The Dyck Language

This language is named after the German mathematician Walther von Dyck, who pioneered the study of groups
using generators.

## The language

$$\Sigma_{\mathcal{D}} := \left\{\left(, \right)\right\}$$
$$\mathcal{D} := \varepsilon | (\mathcal{D})\mathcal{D}$$

## Dyck paths

A Dyck path of length $n$ is a visual representation of all of the words of the Dyck Language which are of the length $n$.

Edges:
- There are two kinds of edges in Dyck Paths.
  - North East edges $(\Delta x, \Delta y) = (1, 1)$ which corresponds to an opening parenthesis.
  - South East edges $(\Delta x, \Delta y) = (1, -1)$ which corresponds to a closing parenthesis.

Vertices:
- Every vertex in a Dyck path represents a substring of a word of length $n$ in the Dyck Language.
- All vertices exist in the first quadrant of the Cartesian plane

### Example
```{.sageplot}
plot(x^2, (x, 0, 10))
```
