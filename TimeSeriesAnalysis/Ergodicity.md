Let $Y_{t}$ be a [[Time Series]]. We call $Y_{t}$ **ergodic** if and only if for arbitrary bounded $g: \mathbb{R}^k\to \mathbb{R}$, $f: \mathbb{R}^m\to \mathbb{R}$:
$$
\begin{align}
\lvert  \mathbb{E}(f(Y_{t},\dots,Y_{t+k})&g(Y_{t+n},\dots,Y_{t+n+m}))\rvert  \\
&\to \lvert\mathbb{E}(f(Y_{t},\dots,Y_{t+k}))  \rvert \lvert \mathbb{E}(g(Y_{t+n},\dots,Y_{t+n+m})) \rvert 
\end{align}
$$
As $n\to \infty$
It is also called **asymptotic independence**.

Any ergodic [[Time Series]] has also an consistent estimator in the sample mean. [[Estimating the mean of a time series]].

## proving ergodicity
We do this usually not by the definition and use the [[Theorem of Brockwell and Davis]]. 