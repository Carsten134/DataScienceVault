Adding to [[Holt's linear method]] we now assume seasonality. So let  $Y_{t}$ be a [[Time Series]] such that (expanding on the [[Additive Components Model]]):
$$
\begin{align}
Y_{t} &= m_{t}+ s_{t}+ u_{t} \\
m_{t} &= m_{t-1}+b_{t-1} + v_{t}  \\
b_{t} &= b_{t-1}+ w_{t} \\
s_{t} &= s_{t-l} + \varepsilon_{t}
\end{align}
$$
Where:
- $m_{t}$ is the trend
- $b_{t}$ is the slope
- $s_{t}$ the seasonal component of period length $l$
- $u_{t}, v_{t}, w_{t}, \varepsilon_{t}$ is iid WN
## Estimation equations
We now determine the trend, the slope and the seasonal component by exponential smoothing. The only difference here is, that we have to take into account the periods of the season:
$$
\hat{s}_{T} = (1-\delta)(y_{T}-\hat{m}_{T})+\delta  \hat{s}_{T-l}
$$
