# Problem 1.1
**a)**
If we have given that:
$$
\sqrt{ n }(X_{n}-c) \overset d\longrightarrow \mathcal N(0, \Sigma)
$$
And we have a continuous and differentiable mapping $\phi(x)$ then we can say that:
$$
\sqrt{ n }(\phi(X_{n})- \phi(c)) \overset d\longrightarrow \mathcal N(0, \phi'(c)\Sigma \phi'(c)')
$$
And so for this we need to find $\phi'(x)$ and do the matrix-multiplication to find the variance of the asymptotic normal
**b)**
$$
\phi'(x,y) = \begin{pmatrix}
\frac{\partial}{\partial x}\phi(x,y) \\
\frac{\partial}{\partial y}\phi(x,y)
\end{pmatrix}' = \begin{pmatrix}
\ln y & \frac{x}{y}
\end{pmatrix}
$$
So inserting this with $\mu$ leads to:
$$
\begin{align}
\phi'(\mu,\mu)\Sigma \phi'(\mu,\mu)' &= \begin{pmatrix}
\ln \mu & 1 
\end{pmatrix}
\begin{pmatrix}
\sigma^2 & 0 \\
0 & \sigma^2
\end{pmatrix}
\begin{pmatrix}
\ln \mu  \\
1
\end{pmatrix} \\

&= \begin{pmatrix}
\ln \mu & 1
\end{pmatrix} \begin{pmatrix}
\sigma^2\ln \mu \\
\sigma ^2 
\end{pmatrix} \\
&= (\ln \mu)^2\sigma^2+ \sigma ^2 \\
&= \sigma^2(\ln(\mu)^2+1)
\end{align}
$$
This leads us to:
$$
\sqrt{ n } (\phi(\bar{X}_{n})-\phi(\mu)) \overset p\longrightarrow \mathcal N(0, \sigma^2(\ln (\mu)^2+1))
$$
**c)**
$$
\phi'(x,y) = \begin{pmatrix}
\frac{1}{y} & -\frac{x}{y^2}
\end{pmatrix}
$$
Inserting $(\mu, \mu)$:
$$
\phi'(\mu, \mu) = \begin{pmatrix}
\frac{1}{\mu} &- \frac{1}{\mu}
\end{pmatrix}
$$
So solving again the matrix multiplication:
$$
\begin{align}
\begin{pmatrix}
\frac{1}{\mu}&-\frac{1}{\mu}
\end{pmatrix}
\begin{pmatrix}
\sigma ^2 & 0 \\
0 & \sigma^2
\end{pmatrix} \begin{pmatrix}
\frac{1}{\mu} \\
-\frac{1}{\mu}
\end{pmatrix} &= \begin{pmatrix}
\frac{1}{\mu}& - \frac{1}{\mu}
\end{pmatrix} \begin{pmatrix}
\frac{\sigma^2}{\mu} \\
-\frac{\sigma^2}{\mu}
\end{pmatrix} \\
&= \frac{\sigma^2}{\mu^2}+ \frac{\sigma ^2}{\mu ^2} \\
&= 2 \frac{\sigma ^2}{\mu^2}
\end{align}
$$
**d)**
$$
\begin{align}
\phi'(x,y) &= \begin{pmatrix}
1 & 1 \\
2x & 2y
\end{pmatrix} \\
\phi'(\mu, \mu) &= \begin{pmatrix}
1 & 1 \\
2\mu & 2 \mu
\end{pmatrix}
\end{align}
$$
Solving for the variance leads to:
$$
\begin{align}
\phi'(\mu, \mu)\Sigma \phi'(\mu,\mu)' &= \begin{pmatrix}
1 & 1  \\
2\mu & 2\mu 
\end{pmatrix} \begin{pmatrix}
\sigma^2 & 0  \\
0 & \sigma ^2
\end{pmatrix}\begin{pmatrix}
1 &2\mu \\
1 & 2 \mu
\end{pmatrix} \\
&= \begin{pmatrix}
1 & 1  \\
2\mu & 2\mu 
\end{pmatrix} \begin{pmatrix}
\sigma ^2 & 2\mu \sigma^2 \\
\sigma ^2 & 2\mu \sigma^2
\end{pmatrix} \\
&= \begin{pmatrix}
2\sigma ^2 & 4\mu \sigma ^2 \\
4\mu \sigma ^2 & 8 \mu^2\sigma ^2
\end{pmatrix} \\
&= \sigma ^2 \begin{pmatrix}
2 & 2\mu  \\
4 \mu & 8 \mu^2
\end{pmatrix}
\end{align}
$$
# Problem 1.2
Using Cramer wold device:
$$
aX_{n}+bY_{n } \overset d \longrightarrow 2a+3b
$$
Through Levy's cont. theorem:
$$
\begin{align}
\varphi_{aX_{n}+ bY_{n}}(t) &\to \varphi_{2a+3b}(t) \\
\varphi_{aX_{n}}(t) \varphi_{bY_{n}}(t)& \to \exp(it 2a)\exp(it 3b) \\
\end{align}
$$
So let an arbitrary $t\in \mathbb{R}$: 
$$
\begin{align}
\mathbb{E}(\exp(itaX_{n})) &= \exp(it 2 a) \frac{n}{n+1}+\frac{1}{n} \\
&\to \exp(it 2a)
\end{align}
$$
Same for $\varphi_{bY_{n}}(t)$:
$$
\begin{align}
\varphi_{b Y_{n}}(t) &= \exp(it 3b) \frac{n}{n+1} + \frac{1}{n}  \\
&\to \exp(it 3b)
\end{align}
$$
So in total the statement holds and convergence in distribution is shown.
# Problem 1.3
Using Levy's theorem:
$$
\begin{align} \varphi_n(t) &= \mathbb E(\exp(itX_n)) \\ &= \sum_{k=1}^n \binom nk \left(\frac\lambda n\right)^k\left(\frac {n-\lambda}n\right)^{n-k}\exp(itk) \\ &= \sum_{k=1}^n \binom nk \left(\frac\lambda n\exp(it)\right)^k\left(\frac {n-\lambda}n\right)^{n-k} \\ &\underset{\text{binom}}= \left(\frac \lambda n\exp(it)+\frac {n-\lambda}n\right)^n \\ &= \left(1+\frac{\lambda(\exp(it)-1)}{n}\right)^n  \\
&= \exp(\lambda(\exp(it)-1))
\end{align}
$$
And for the poisson:
$$
\begin{align*} \varphi_P(t) &= \mathbb E(\exp(itX)) \\ &= \sum_{k=1}^\infty \exp(itk)\frac{\lambda^k}{k!}\exp(-\lambda) \\ &= \exp(-\lambda)\sum _{k=1}^n \frac{(\exp(it)\lambda)^k}{k!} \\ &\underset{\text{hint}}= \exp(-\lambda)\exp(\exp(it)\lambda) \\ &= \exp(\lambda(\exp(it)-1)) \end{align*}
$$
# Problem 2.1
**a)**
$$
\begin{align}
\mathscr X &= \mathbb{R}_{+}^n \\
\Theta &= \mathbb{R}_{+} \\
D &= \begin{cases}
\delta_{0} \\
\delta_{1}
\end{cases} \\
L &= \text{0-1 loss}
\end{align}
$$
**b), c) and d)** 
One parameter exponential distributions are defined by:
$$
c(\theta)\tilde{h}(x)\exp(Q(\theta)S(x))
$$
so:
$$
\begin{align}
c(\theta) &= \frac{1}{\theta} \\
\tilde{h}(x) &= 1 \\
Q(\theta) &= \frac{1}{\theta} \\
S(x) &= -x
\end{align}
$$
And since $Q(\theta)$ is monotonic, we can say, that the likelihood is monotonic and therefore that $\Phi(\vec{X)}$ is UMP.

**e)**
$$
R(\delta,\theta) = \begin{cases}
P(t(\vec{X})> c) + \gamma P(t(\vec{X}) = c) & \theta\leq \theta_{0} \\
P(t(\vec{X})< c )+ (1-\gamma)P(t(\vec{X}) =c) & \theta > \theta_{0}
\end{cases}
$$
# Problem 2.2
**b)**
$$
\begin{align}
\mathcal L (\vec{X}|\theta) &= \frac{1}{\theta^n} \exp\left( -\frac{1}{\theta} \sum_{i=1}^n x_{i} \right)
\end{align}
$$
Log:
$$
\begin{align}
\ln \mathcal L(\vec{X}|\theta) &= -n \ln \theta - \frac{1}{\theta}\sum_{i=1}^n x_{i}
\end{align}
$$
First order condition:
$$
\begin{align}
-\frac{n}{\theta} + \frac{1}{\theta ^2} \sum_{i=1}^n x_{i} &= 0 \\
-n +\frac{1}{\theta}\sum_{i=1}^n x_{i}& =0 \\
\theta &= \frac{1}{n} \sum_{i=1}^nx_{i}
\end{align}
$$
**c)**
Risk using bias variance decomp:
$$
\begin{align}
\mathbb{E}(\bar{X}_{n})  &= \frac{1}{n}\sum_{i=1}^n \mathbb{E}(X_{i}) \\
&= \frac{n}{n}\theta = \theta
\end{align}
$$
Variance:
$$
\begin{align}
Var(\bar{X}_{n}) &= \frac{1}{n^2} \sum_{i=1}^n Var(X_{i}) \\
&= \frac{n}{n^2}\theta ^2  \\
&= \frac{\theta ^2}{n}
\end{align}
$$
**d)**
$$
\begin{align}
\frac{\partial\ln \mathcal L(\vec{X}|\theta)}{\partial \theta} &= - \frac{n}{\theta} + \frac{1}{\theta ^2 } \sum_{i=1}^n X_{i} \\
\frac{\partial ^2 \ln \mathcal L(\vec{X}|\theta)}{\partial^2 \theta ^2} &= \frac{n}{\theta ^2 } - \frac{2}{\theta ^3} \sum_{i=1}^n X_{i}
\end{align}
$$
Now the expectation of that:
$$
\begin{align}
\mathbb{E}\left( \frac{\partial ^2 \ln \mathcal L(\vec{X}|\theta)}{\partial^2 \theta ^2}  \right) &= \frac{n}{\theta^2}-\frac{2}{\theta^3} \sum_{i=1}^n \mathbb{E}(X_{i}) \\
&= \frac{n}{\theta ^2 }- \frac{2}{\theta^3} n \theta \\
&= - \frac{n}{\theta ^2}
\end{align}
$$
And now since we square everything, the (-1) in front falls away and we're left with:
$$
\frac{1}{\mathbb{E}\left( \frac{\partial \ln \mathcal L(\vec{X}|\theta)}{\partial\theta }  \right) ^2} = \frac{\theta^2}{n}
$$
**e)**
So yes, the risk is the lower bound, therefore the ML-estimator is admissible for unbiased rules.