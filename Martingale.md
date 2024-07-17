Let $Y_{t}$ be a [[Time Series]] with $\mathbb{E}(Y_{t})<\infty$ for all $t\in \mathbb{I}$ . Where $\mathbb I$ is linearly ordered. Then we can say (if $Y_{t}$ is a **Martingale**):
$$
\mathbb{E}(X_{t+1}|X_{t},\dots,X_{1}) = X_{t}
$$
For all $t$ and there is an increasing sequence of [[Sigma Algebra]]s $\mathcal F_{t}$ where:
$$
\mathcal F_{t}\subset \mathcal F_{t+1}
$$
And it hold that:
$$
\mathbb{E}(X_{t+1}|\mathcal F_{t}) =X_{t}
$$
