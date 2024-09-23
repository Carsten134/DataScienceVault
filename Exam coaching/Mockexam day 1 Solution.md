# Problem 1.1
**a)**
$$
\begin{align}
\emptyset &\in \mathcal A \\
A\in\mathcal A &\implies A^c\in\mathcal A \\
(A_{n})_{n\in\mathbb N} \in\mathcal A &\implies \bigcup_{i=1}^\infty A_{i}\in\mathcal A
\end{align}
$$
**b)**
$$
\{\{1\},\{2,3,4\}, \{1,2,3,4\}, \emptyset\}
$$
**c)**
It generally holds, that $\mathcal P(\Omega)$ is the biggest possible sigma algebra. Since $\mathcal{A}\in \mathcal P(\Omega)$:
$$
\mathcal{A}\cup \mathcal{A}_{2} = \mathcal{A}_{2}
$$
Which is a $\sigma$-Algebra. Meaning, yes the union of $\mathcal{A}$ and $\mathcal{A}_{2}$ is a $\sigma$-Algebra.
**d)**
Showing by way of $L_{1}$ convergence:
$$
\begin{align}
\mathbb{E}(|X_{n}-1|) &= |1-1| P(X_{n}=1)+|2-1| P(X_{n}= 2) \\
&= 0 P(X_{n} = 1)+ P(X_{n}=2) \\
&= \frac{1}{n}\to 0
\end{align}
$$
Since $L_{1}$ holds, convergence in probability also holds.
**e)**
$$
\begin{align}
\mathbb{E}(\exp(itX)) &= \exp(it)P(X_{n} = 1)+ \exp(2it)P(X_{n} = 2) \\
&= \exp(it)  \frac{n-1}{n} + \exp(2it)   \frac{1}{n} \\
&\to \exp(it) = \varphi_{1}(t)
\end{align}
$$
And now using Levy's cont. theorem this is equivalent to:
$$
X_{n} \overset d\longrightarrow 1
$$
# Problem 2.1
**a)**
$$
\begin{align}
\mathscr X &= \mathbb{R}_{+}^n \\
\Theta &= (0, \infty) \\
D &= \Theta \\
L &= \left( \delta-\frac{1}{\theta} \right)^2
\end{align}
$$
**b)**
Likelihood:
$$
\begin{align}
\mathcal L(\vec{X}|\theta) &= \prod_{i=1}^n \theta \exp(-\theta x_{i}) \\
&=\theta^n \exp\left( -\theta \sum_{i=1}^n x_{i} \right) 

\end{align}
$$
Log likelihood:
$$
\begin{align}
\ln \mathcal L(\vec{X}|\theta) &= n \ln(\theta)-\theta \sum_{i=1}^n x_{i}
\end{align}
$$
First order condition:
$$
\begin{align}
\frac{\partial}{\partial \theta} \ln \mathcal L(\vec{X}|\theta) &= \frac{n}{\theta}-\sum_{i=1}^n x_{i} = 0 \\
\Longleftrightarrow \frac{n}{\theta} &= \sum_{i=1}^n x_{i} \\
\Longleftrightarrow \hat{ \theta}_{ML} &= \frac{1}{\bar{X}_{n}}
\end{align}
$$
Second order condition:
$$
-\frac{1}{\theta^2} < 0 \hspace{1em} \forall \theta >\Theta
$$
And since $\mathbb{E}(X) =\frac{1}{\theta}$ we now know that:
$$
\hat{\mathbb{E}}(X)_{ML} = \bar{X}_{n}
$$
**c)**
Using Bias variance decomp.
$$
\begin{align}
R(\hat{\mathbb{E}}(X)_{ML}, \theta) &=  Var(\hat{\mathbb{E}}(X)_{ML}) + Bias(\hat{\mathbb{E}}(X)_{ML})^2 \\
&= Var(\bar{X}_{n})+ Bias(\bar{X}_{n})^2 \\
&= \frac{1}{\theta^2n}+ \left[ \mathbb{E}(\bar{X}_{n})-\frac{1}{\theta}\right]^2 \\
&= \frac{1}{\theta^2n} 
\end{align}
$$
**d)**
$$
\begin{align}
\mathbb{E}(\hat{\theta}_{2}) &= \frac{1}{n+1} \sum_{i=1}^n \mathbb{E}(X_{i}) \\
&= \frac{n}{n+1} \frac{1}{\theta}
\end{align}
$$
And so the squared bias is:
$$
\begin{align}
\left( \mathbb{E}(\hat{\theta}_{2}) -\frac{1}{\theta}\right)^2 &= \frac{1}{(n+1)^2} \frac{1}{\theta^2} 
\end{align}
$$
We can compute the variance using the iid property like in c):
$$
\begin{align}
Var(\hat{\theta}_{2}) &= \frac{1}{(n+1)^2} \sum_{i=1}^n Var(X_{i}) \\
&= \frac{n}{(n+1)^2} \frac{1}{\theta ^2}
\end{align}
$$
Finally we can compute the risk:
$$
\begin{align}
R(\hat{\theta}_{2}, \theta) &= \frac{1}{(n+1)^2} \frac{1}{\theta^2} + \frac{n}{(n+1)^2} \frac{1}{\theta ^2} \\
&= \frac{n+1}{(n+1)^2 } \frac{1}{\theta^2} \\
&= \frac{1}{n+1} \frac{1}{\theta ^2} < \frac{1}{n} \frac{1}{\theta ^2 } = R(\hat{ \mathbb{E}}(X)_{ML}) 
\end{align}
$$
So the risk is better, than the ML-estimator.