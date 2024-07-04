If the variance of a [[Time Series]] $Y_{t}$ is proportional to the mean like so:
$$
\sigma_{t} = k \mu_{t}^\alpha
$$
you can use a **Box Cox Transformation**. It is defined this way:
$$
y_{t}^{(\lambda)} = \begin{cases}
\frac{(y_{t}+c)^\lambda-1}{\lambda} & \text{for }\lambda \neq 0\\
\ln(y_{t}+c) & \text{for }\lambda = 0
\end{cases}
$$
So this can partially be a procedure to fix the [[Time Series]], if it has no [[weak stationarity]].

You optian $\lambda = 1-\alpha$ by deviding the time series into $j$ periods and estimating the standard deviation in every period ($s_{i}$) regressing:
$$
\ln(s_{i}) = c+\alpha \ln(\bar{y_{i}})
$$
And then use OLS and set  $\lambda = 1-\hat{\alpha}$.