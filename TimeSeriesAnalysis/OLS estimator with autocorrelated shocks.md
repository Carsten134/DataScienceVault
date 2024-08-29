we want to regress:
$$
X_{t} = \beta_{0}+\beta_{1}t+\varepsilon_{t}
$$
And:
$$
Cov(\varepsilon_{t}, \varepsilon_{t-1}) = \rho \sigma^2
$$
Translating to matrix notation:
$$
Z = \begin{pmatrix}
1 & 1 \\
1 & 2 \\
1 & 3 \\
\vdots  & \vdots \\
1  & T 
\end{pmatrix}
\hspace{1em} X^{(T)} = \begin{pmatrix}
X_{1} \\
X_{2} \\
\vdots \\
X_{T}
\end{pmatrix}
$$
And we can write:
$$
X^{(T)} = Z^{(T)}\beta+\varepsilon^{(T)}
$$
According to OLS the estimator for $\beta$ is:
$$
\begin{align}
\hat{\beta} &= (Z^TZ)^{-1}Z^TX^{(T)} \\
&= (Z^TZ)^{-1}Z^T(Z^{(T)}\beta + \varepsilon) \\
&= \beta + (Z^TZ)^{-1}Z^T\varepsilon
\end{align}
$$
Now assessing the variance:
$$
\begin{align}
Var(\hat{\beta}) &= Var(\beta+(Z^TZ)^{-1}Z^T\varepsilon) \\
&= Var((Z^TZ)^{-1}Z^T\varepsilon) \\
&= (Z^TZ)^{-1}Z^TVar(\varepsilon)((Z^TZ)^{-1}Z^T)^T \\
&= (Z^TZ)^{-1}Z^T\Sigma_{\varepsilon}((Z^TZ)^{-1}Z^T)^T  \\
&= (Z^TZ)^{-1}Z^T\Sigma_{\varepsilon}Z(ZZ^T)^{-1}
\end{align}
$$
We get $Var(\hat{\beta_{0}})$ and $Var(\hat{\beta_{1}})$ by:
$$
Var(\hat{\beta_{0}}) = Var(\hat{\beta})_{1,1} \hspace{1em} Var(\hat{\beta_{1}}) = Var(\hat{\beta})_{2,2}
$$
