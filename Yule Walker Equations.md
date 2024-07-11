#timeseriesanlysis #linearalgebra 
Looking at the [[AR process]] equation:
$$
Y_{t} = \phi_{1}Y_{t-1}+\phi_{2}Y_{t-2}+\dots+\phi_{p}Y_{t-p}
$$
And taking the expected value:
$$
\mathbb{E}(Y_{t}) = \phi_{1}\mathbb{E}(Y_{t-1})+\dots +\phi_{p}\mathbb{E}(Y_{t-p})
$$
And multiplying with $Y_{t}$:
$$
\mathbb{E}(Y_{t}^2) = \phi_{1}\mathbb{E}(Y_{t-1}Y_{t})+\dots \phi_{p}\mathbb{E}(Y_{t-p}Y_{t})
$$
And assuming $w_{t}\sim WN(0,\sigma^2)$ then we have:
$$
\gamma_{0} = \phi_{1}\gamma_{1}+\dots+\phi_{p}\gamma_{p}
$$
But note that we can do this for any lag so we end up with:
$$
\gamma_{h} = \phi_{1}\gamma_{h-1}+\dots+\phi_{p}\gamma_{h-p}
$$
This is a system of $p$ equations so we can solve for $\phi_{i}$:
$$
\begin{align}
\begin{pmatrix}
\rho_{1} \\
\vdots  \\
\rho_{p}
\end{pmatrix} &= \begin{pmatrix}
\rho_{0} & \rho_{1}  & \dots  & \rho_{p-1} \\
\vdots  & \vdots & \vdots & \vdots \\
\rho_{p-1} & \dots  & \dots  & \rho_{0}
\end{pmatrix}\begin{pmatrix}
\phi_{1} \\
\vdots \\
\phi_{p}
\end{pmatrix} \\
\rho &= \Gamma \phi
\end{align}
$$
This is now solvable by:
$$
\Gamma ^{-1}\rho = \phi
 $$
 This is also just a [[Moment estimator]].
