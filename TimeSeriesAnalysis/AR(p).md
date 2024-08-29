Let $Y_{t}$ be a [[Time Series]]. $Y_{t}$ can be described as an AR(p) process iff:
$$
Y_{t} = c+\phi_{1}Y_{t-1}+\dots+\phi_{p}Y_{t-p}+w_{t}, \hspace{1em} \forall t \in \mathbb{Z}
$$
Alternatively you can notate:
$$
\begin{align}
(1-\phi_{1}B-\dots-\phi_{p}B^p)Y_{t} &= c + w_{t}  \\
\phi(B)Y_{t} &= c+w_{t}
\end{align}
$$
Where $\phi_{t}$ is the **autoregressive operator**.
## stationarity
If $\phi ^{-1}(B)$ exists, the [[Wold decomposition]] of this process is:
$$
Y_{t} = \phi ^{-1}(B)(c+w_{t})
$$
So the process is only stationary iff the inverse of the autoregressive operator exists.