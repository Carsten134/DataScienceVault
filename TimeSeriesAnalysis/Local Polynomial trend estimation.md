Consider the setup:
$$
\begin{align}
y_{t} &= m_{t}+u_{t} \\
m_{t+i} &= \beta_{0,t}+\beta_{1,t}i+\dots+\beta_{p,t}i^p
\end{align}
$$
Estimation is on a time-window of length $k_{1}+k_{2}$. So between $y_{t-k_{1}}$ and $y_{t+k_{2}}$
- additional restrictions include $k_{1}+k_{2} \geq p+1$
# Symmetrical time-window
We can express this as:
$$
y_{t}^{(k)} = Z\beta_{t}+u_{t}^{(k)}
$$
Where $y_{t}^{(k)}$ can be expressed as a vector:
$$
y_{t}^{(k)} =\begin{pmatrix}
y_{t-k} \\
\vdots  \\
y_{t+k}
\end{pmatrix}, u_{t}^{(k)} = \begin{pmatrix}
u_{t-k} \\
\vdots \\
u_{t+k}
\end{pmatrix}
$$
And $Z$ is the regressor matrix:
$$
Z = \begin{pmatrix}
1 & -k & (-k)^2 & \dots & (-k)^p \\
\vdots & \vdots & \vdots & \vdots & \vdots \\
1 & 0 & 0 & \dots & 0 \\
\vdots & \vdots & \vdots & \vdots & \vdots \\
1 & k & k^2 & \dots & k^p 
\end{pmatrix}
$$
using [[OLS]] to estimate $\beta_{t}$ leads to:
$$
\hat{\beta}_{t} = (Z^TZ)^{-1}Z^Ty_{t}^{(k)}
$$
- Can also be determined by [[Cramers rule]].
- Further it should be noted, that we are mainly interested in $\beta_{0,t}$
	- $\beta_{0,t}$ is gained by a moving average with symmetrical weights
	- Following properties hold for the weights $\theta_{j}$:
		- **symmetry**: $\theta_{j} = \theta_{-j}$
		- **adding up to one**: $\sum_{j=-k}^k\theta_{j} = 1$
		- **square sum equal to $\theta_{0}$**: $\sum_{j=-k}^k \theta_{j}^2 = \theta_{0}$

# Local polynomial trend estimation is a [[smoothing method]]. 
We can assess the smoothing with the **variance** reduction factor, which resulting from our model assumptions is equal to:
$$
Var(\hat{m}_{t}) = \sigma^2\sum_{j=-k}^k \theta_{j}^2  =\sigma^2\theta_{0}
$$
