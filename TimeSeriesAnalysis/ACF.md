#timeseriesanlysis 
Let $X_{t}$ be a [[Time Series]]. Then the ACF $\rho (h)$ is defined as:
$$
\rho(h) = \frac{Cov(X_{t},X_{t-h})}{Var(X_{t})}
$$
Using the [[Theoretical autocovariance function]] we can simplify $p(h)$ to:
$$
\rho(h) = \frac{\gamma(h)}{\gamma(0)}
$$
The ACF gives you some clues about the a [[Time Series]] and the random process behind it. 