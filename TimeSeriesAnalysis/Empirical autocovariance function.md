#timeseriesanlysis 
Let $y_{t}$ be a [[Time Series]]. Then the empirical autocovariance function is defined as:
$$
\hat{\gamma}(h) = \frac{1}{T}\sum_{t=T_{1}}^{T_{2}}(y_{t+h}-\bar{y})(y_{t}-\bar{y})
$$
Where $T_{1}=\max(1,1-h)$ and $T_{2}=\min(T,T-h)$.
It is a estimate of the [[Theoretical autocovariance function]] 