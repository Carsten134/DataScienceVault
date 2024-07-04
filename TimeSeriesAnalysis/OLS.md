#timeseriesanlysis #stattheory 
Ordinary least squares. 
Let $Y$ be a [[Random Variable]]. Additionally we assume a realized sample from these random variables $\{(x_{1},y_{1}),\dots,(x_{n},y_{n})\}$. And assume the model:
$$
y_{i} = f(x_{i}, \beta) +\varepsilon_{i}
$$
The input $\beta\in \mathbb{R}^p$ is some parameter vector and $x_{i}$  is exogenous and deterministic. We want to find the $\beta$, that gives us the best goodness of fit. With OLS we minimize the squared sums over all [[observations]]:
$$
\min_{\beta\in \mathbb{R}^p} \sum_{i=1}^n(y_{i}-f(x_{i},\beta))^2
$$
## special cases
If the model $f(x_{i}, \beta)$ is of the form:
$$
y_{i} = \beta_{0}+\beta_{1}x_{i}+ \varepsilon_{i}
$$
Then the [[Projection Theorem]] provides the best linear estimate through the normal equations. 
