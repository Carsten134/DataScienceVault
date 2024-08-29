The special case of the [[AR(p)]] process is very interesting to derive basic properties from:
$$
(1-\phi B)Y_{t} = c+w_{t}
$$
# Stationarity
The autoregressive operator is invertible if and only if:
$$
\exists \phi ^{-1}(B) \Longleftrightarrow \lvert \phi \rvert< 1 
$$
In that case the inverse is:
$$
\phi ^{-1}(B) = \frac{1}{1-\phi B} = \sum_{i=0}^\infty (\phi B)^i
$$
# expected value
The expected value only exists if the AR(1) process is stationary. In that case:
$$
\begin{align}
\mathbb{E}(Y_{t})&= \mathbb{E}(\phi ^{-1}(B)(c+w_{t})) \\
&= \mathbb{E}\left( \sum_{i=0}^\infty (\phi B)^i (c+w_{t})\right) \\
&=  \mathbb{E} \left( \sum_{i=1}^\infty \phi^ic+\sum_{i=0}^\infty \phi^iw_{t-i} \right) \\
&=c \sum_{i=0}^\infty \phi^i +\sum_{i=0}^\infty \phi^i\mathbb{E}(w_{t-i}) \\
&= \frac{c}{1-\phi} +0
\end{align}
$$
# Autocovariance
The demeaned time-series $\tilde{Y_{t}} = Y_{t}-\mathbb{E}(Y_{t})$ has then the autocovariance:
$$
\begin{align}
Cov(\tilde{Y_{t}}, \tilde{Y}_{t+h}) &= \mathbb{E}(\tilde{Y}_{t}\tilde{Y}_{t+h}) \\
&= \mathbb{E}\left( \left( \sum_{i=0}^\infty \phi^iw_{t-i} \right)  \left( \sum_{i=0}^\infty \phi^iw_{t+h-i} \right) \right) \\
&\vdots \\
&= \sum_{i=0}^\infty \phi^i\phi^{i+h}\sigma^2 \\
&= \frac{\phi^h\sigma^2}{1-\phi^{2}}
\end{align}
$$