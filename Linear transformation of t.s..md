We define a **finite** linear transformation $W$ of a realized [[Time Series]] $y_{t}$ as:
$$
W y_{t} = \sum_{j=-k}^Iw_{j}y_{t-j} = \sum_{j=-k}^Iw_{j}B^jy_{t}
$$
Where $B$ is the [[Lag Operator]].
## special cases:
1. first difference:
	- Is notated as: $\Delta y_{t}$ and is $W = 1-B$
- p-difference:
	- $\Delta_{p} = 1-B^p$
- difference of order p:
	- $\Delta^p = (1-B)^p$

## Elimination of polynomial trends
If we assume the [[Additive Components Model]] with:
$$
m_{t} = \beta_{0}+\beta_{1}t+\dots+\beta_{p}t^p
$$
Then it holds that (can be proven by [[induction]]):
$$
\Delta^{p+1}m_{t} =0
$$
## application in practice
Apply $\Delta$ until you get a stationary behaving timeseries.

We differentiate between [[high and low pass filters]].