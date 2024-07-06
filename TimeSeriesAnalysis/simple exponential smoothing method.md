#timeseriesanlysis 
Is a method for **short-term-forecasting** a [[Time Series]] $Y_{t}$ **without a systematic pattern**. 
Consider the time-series:
$$
Y_{t} = m+\varepsilon_{t}\hspace{1em} \varepsilon_{t}\sim i.i.d. (0, \sigma^2)
$$
We can now calculate a new observation into the future $y_{T+1}$ with:
$$
\hat{y}_{T+1} = \frac{T-1}{T}\bar{y}_{T-1}+ \frac{1}{T}y_{T}
$$
If we abstract from these weights we can rewrite this as:
$$
\hat{y}_{T+1} = \theta  \bar{y}_{T-1}+(1-\theta)y_{T}
$$
## Flat forecast
$$
\hat{y}_{T+k} = \hat{y}_{T+1} \hspace{1em} \forall k \in \mathbb{N}
$$
## Es forecast
$$
\hat{y}_{T}(1) = \hat{y}_{T-1}(1)+(1-\theta)(y_{T}-\hat{y}_{T-1}(1))
$$
So the new prediction is corrected by the error of the last prediction
## Relation to [[OLS]]
If we assume the [[Additive Components Model]] on the [[Time Series]] $Y_{t}$ like so:
$$
Y_{t} = m_{t}+ \varepsilon_{t}\hspace{1em} \varepsilon_{t}\sim i.i.d. (0,\sigma^2)
$$
And we choose to optimize the loss:
$$
\min_{\hat{y}_{T+1}} \sum_{i=1}^Tw_{t}(y_{t}-\hat{y}_{T+1})
$$
With the weights:
$$
w_{T} = c, w_{T-1} = c\theta, w_{T-2} = c\theta^2,\dots
$$
And the additional constraint:
$$
\sum_{t=1}^Tw_{t} = 1
$$
We get that:
$$
c\sum_{t=1}^T\theta^t \to c\frac{1}{1-\theta} = 1 \implies c = 1-\theta
$$
Keeping this in mind the loss optimal solution for $\hat{y}_{T+1}$ is:
$$
\hat{y}_{T+1} = \frac{\sum_{t=1}^Tw_{t}y_{t}}{\sum_{t=1}^Tw_{t}}
$$
And with $T\to \infty$ and $c = 1-\theta$ we get:
$$
w_{T} = 1-\theta, w_{T-1}=(1-\theta)\theta, w_{T-2}=(1-\theta)\theta^2
$$
Which leads to the approximation:
$$
\hat{y}_{T+1}\approx(1-\theta)\sum_{t=1}^T\theta^{T-t}y_{t}
$$
# choice of $\theta$:
- $\theta \approx 1$ -> stronger smoothing
- $\theta \approx 0$ -> forecast almost solely determined by last observation
- Or do [[OLS]] on quadratic loss with 
