Let $y_{t}$ be trajectory of a [[weak stationarity]] [[Time Series]] $Y_{t}$. Then we can compute the expected value of the time series by the arthmetic mean:
$$
\mathbb{E}(Y_{t}) = \mu = \frac{1}{n}\sum_{t=1}^Ty_{t} = \bar{Y}_{T}
$$
## relation to autocorrelation
We can then compute the variance of the estimator:
$$
\begin{align}
Var(\bar{Y}_{T}) &= Var\left( \frac{1}{n}\sum_{t=1}^T y_{t} \right)  \\
&= \frac{1}{T^2}\left( \sum_{t=1}^TVar(Y_{t})+\sum_{j \neq i}Cov(Y_{i}, Y_{j}) \right)  \\
&= \frac{1}{T^2} \left( T \gamma_{0}+2\sum_{t=1}^T\sum_{k = t+1}^T\gamma_{k} \right)  \\
&= \frac{\gamma_{0}}{T}\left( 1+2\sum_{k=1}^{T-1}\left( 1-\frac{k}{T} \right)\rho_{k} \right) 
\end{align}
$$
This means, that the variance decreases, if the autocorrelation is smaller than zero. But increases, if the autocorrelation is larger than 0.

here an example:
![[Pasted image 20240711185407.png]]
It takes longer to find the mean because the timeseries oscilates less

And for $\theta = -0.9$ we get:
![[Pasted image 20240711185509.png]]Here it is much easier to estimate the mean