#montecarlo #algorithm 
Takes advantage of the [[Law of large numbers]]: 
$$
\int_{\mathbb{R}}g(x)p(x)dx = \mathbb{E}(g(x))
$$
So we can sample from $p(x)$ and estimate $\mathbb{E}(g(x))$ with the sample average:
$$
\frac{1}{n}\sum_{i=1}^ng(x_{i})\to\mathbb{E}(g(x)) 
$$
This way we can approximate, integrals that are difficult to solve analytically.

## findings from the group
- It seemed like the **uniform distribution** yielded the best accuracy