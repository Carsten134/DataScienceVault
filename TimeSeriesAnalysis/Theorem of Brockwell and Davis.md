Let $Y_{t}$ be a [[weak stationarity]] [[Time Series]] with $$
\begin{align}
\mathbb{E}(Y_{t}) &= \mu \\
\gamma(h) &= \mathbb{E}((Y_{t+h}-\mu)(Y_{t}-\mu))
\end{align}
$$
And then as $T \to \infty$ we get two implications:
$$
\begin{align}
\gamma(h)\to 0\text{ as } h\to 0 &\implies Var(\bar{Y}_{T})\to 0  \\

\sum_{k\in \mathbb{Z}}\lvert \gamma(h) \rvert<\infty &\implies T(\mathbb{E}(\bar{Y}_{T}-\mu)^2)\to \sum_{k\in \mathbb{Z}}\gamma(h)
\end{align}
$$
Where:
$$
\bar{Y}_{T} = \frac{1}{n}\sum_{t=1}^ny_{t}
$$
is the arithmetic mean of the timeseries sample: $\{y_{1},\dots,y_{T}\}$
