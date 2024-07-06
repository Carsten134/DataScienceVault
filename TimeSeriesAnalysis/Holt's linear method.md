#timeseriesanlysis #forecasting
## Setup
Let $Y_{t}$ be a [[Time Series]] with the [[Additive Components Model]]:
$$
\begin{align}
y_{t} &= m_{t}+u_{t}\\ 
m_{t} &= m_{t-1}+b_{t-1}+v_{t} \\
b_{t} &= b_{t-1}+w_{t}
\end{align}
$$
where:
- $u_{t}, v_{t}, w_{t}$ are i.i.d. $\mathcal N(0, \sigma^2)$ are the shocks. 
- $m_{t}$ is the trend
- $b_{t}$ is the slope and the first difference of the trend $m_{t}$
- Contrary to [[simple exponential smoothing method]] we assume structure of the [[Time Series]] in the sense, that we assume a trend
**simulation of the setup**:
![[Pasted image 20240705160607.png]]
## The equations
$$
\begin{align}
\hat{y}_{T-1}(1) &= \hat{m}_{T-1}(1) = \hat{m}_{T-1}(0)+\hat{b}_{T-1}(0)  \\
\hat{m}_{T}(0) &= \hat{m}_{T-1}(1)+(1-\theta)(y_{T}-\hat{y}_{T-1}(1)) \\
\hat{b}_{T}(0) &= \hat{b}_{T-1}(0)+(1-\gamma)(\hat{m}_{T}(0)-\hat{m}_{T-1}(0)-\hat{b}_{T-1})
\end{align}
$$
1. Frist is the forecasting equation
2. The other two are smoothing 
	- Therefore $\theta,\gamma$ are smoothing parameters
	- choose them like the [[simple exponential smoothing method]]