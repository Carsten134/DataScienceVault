# Problem 3.1
**1.**
First state the general problem:
$$
\hat{\theta}_{ML} = \arg \max_{\theta\in \Theta}\mathcal L(x|\theta) = \arg \max_{\theta\in \Theta}\ln\mathcal L(x|\theta)
$$
Maximum likelihood function:
$$
\begin{align}
\mathcal L(x|\theta) &= \prod_{i=1}^nf(x_{i}|\theta) \\
&= \prod_{i=1}^n \frac{1}{\theta}\exp \left( -\frac{x_{i}}{\theta} \right)  \\
&= \theta^{-n}\exp \left( -\frac{1}{\theta}\sum_{i=1}^nx_{i} \right) 
\end{align}
$$
Now log likelihood:
$$
\begin{align}
\ln \mathcal L(x|\theta) &= -n\ln \theta-\frac{1}{\theta}\sum_{i=1}^nx_{i}
\end{align}
$$
FOC:
$$
\begin{align}
 \frac{\partial \ln \mathcal L(x|\theta)}{\partial \theta} &= -\frac{n}{\theta}+\frac{1}{\theta^2} \sum_{i=1}^nx_{i} = 0 \\ \frac{1}{\theta}\sum_{i=1}^nx_{i} &= n \\
\theta_{ML} &= \bar{X}_{n}
\end{align}
$$
SOC:
$$
\begin{align}
\ln \mathcal L''(x|\theta) &= \frac{n}{\theta^2} - \frac{2}{\theta^3} \sum_{i=1}^nx_{i}  \\
&= \frac{n}{\theta^2}-\frac{2n}{\theta^3}\bar{X}_{n}
\end{align}
$$
Means, if we check at $x = \bar{X}_{n}$:
$$
\begin{align}
\ln \mathcal L''(\bar{X}_{n}|\theta) &= \frac{n}{(\bar{X}_{n})^2}-\frac{2n}{(\bar{X}_{n})^3}\bar{X}_{n} \\
&= \frac{n-2n}{\bar{X}_{n}^2} <0
\end{align}
$$
**2.**
Unbiasedness $\mathbb{E}(\bar{X}_{n}) = \theta$:
$$
\begin{align}
\mathbb{E}(\bar{X}_{n}) &= \mathbb{E}\left( \frac{1}{n}\sum_{i=1}^nX_{i} \right) \\
&= \frac{1}{n}\sum_{i=1}^n\mathbb{E}(X_{i}) \\
&= \frac{1}{n}\sum_{i=1}^n\theta \\
&= \frac{n}{n}\theta = \theta 
\end{align}
$$
Variance:
$$
\begin{align}
Var(\bar{X}_{n}) &= \frac{1}{n^2} Var\left( \sum_{i=1}^n X_{i} \right)  \\
&= \frac{1}{n^2} \sum_{i=1}^n Var(X_{i}) \hspace{1em} \text{iid} \\
&= \frac{n}{n^2} \theta^2 = \frac{\theta^2}{n}
\end{align}
$$
**3.**
Bias variance decomposition:
$$
\begin{align}
R(\delta, \theta) &= \mathbb{E}((\delta(X)-\theta)^2) \\
&= Bias(\delta)^2 + Var(\delta)
\end{align}
$$
But as we look only at unbiased estimators our risk becomes:
$$
R(\delta, \theta) = Var(\delta)
$$
And because $Var(\bar{X}_{n}) = \frac{\theta^2}{n}$ and therefore has the lowest variance, it also has the lowest risk and is therefore admissible.

**4.**
First compute the bias:
$$
\begin{align}
\mathbb{E}(\hat{\theta}_{2}) &= \mathbb{E}\left( \frac{1}{n+1}\sum_{i=1}^nX_{i} \right)  \\
&= \frac{1}{n+1}\sum_{i=1}^n\mathbb{E}(X_{i}) \\
&= \frac{n}{n+1}\theta \\
\implies Bias(\hat{\theta}_{2}) &= \frac{n}{n+1}\theta-\theta \\
&= -\frac{1}{n+1}\theta
\end{align}
$$
Then compute the variance
$$
\begin{align}
Var(\hat{\theta}_{2}) &= \frac{1}{(n+1)^2}\sum_{i=1}^n Var(X_{i}) \\
&=  \frac{n}{(n+1)^2}\theta ^2 \\
\end{align}
$$
And finally combine in the Bias variance decomposition:
$$
\begin{align}
 R(\hat{\theta}_{2},\theta) &= Bias(\hat{\theta}_{2})^2+ Var(\hat{\theta}_{2}) \\
&= \frac{1}{(n+1)^2}\theta ^2 + \frac{n}{(n+1) ^2}\theta ^2 \\
&= \frac{(n+1)}{(n+1)^2}\theta ^2 \\
&= \frac{1}{n+1}\theta^2 < \frac{1}{n}\theta^2 = R(L(\hat{\theta}_{ML}, \theta))
\end{align}
$$
So even-though the max. likelihood est. is an admissible unbiased estimator, the estimator is not overall admissible.
# Problem 3.2
**1.**
$$
\begin{align}
 \Theta & = (0,1) \\
\mathscr X &= \{0,..,k\}^n \\
D &= [0,1]\\
L &= L(\theta,d) = \min \left\{2, \left( \frac{d-\theta}{\theta} \right)^2 \right\}
\end{align}
$$
**2.**
Let $\delta_{M}\in D$ a decision rule, then $\delta_{M}$ is minimax iff:
$$
\sup_{\theta\in\Theta} R(\delta, \theta) = \inf_{\delta\in D}\sup_{\theta\in \Theta}R(\delta, \theta)
$$
Where $R$ is the expected loss under parameter $\theta$.
**3.**
$$
L(\theta, \delta_{0}) =\min \left\{2,\left( -\frac{\theta}{\theta} \right)^2 \right\} = 1 \hspace{1em} \forall \theta\in \Theta
$$
If we were to choose another randomized rule, this rule would need to be positive $\delta(X) = c>0$ on set $B_{\delta}$. 
In that case it would hold, that:
$$
\exists \hat{\theta} \in (0,1): \left( \frac{c-\hat{\theta}}{\hat{\theta}} \right)^2 > 2 \implies  L(\delta, \hat{\theta}) =2 \hspace{1em} \forall x\in B_{\delta}
$$
In that case the risk becomes:
$$
\begin{align}
R(\delta, \hat{\theta}) &= \sum_{x\in B_{\delta}^c} L(0,\hat{\theta})f(\vec{x}|\hat{\theta}) + \sum_{x\in B_{\delta}}L(\delta, \hat{\theta})f(\vec{x}|\hat{\theta}) \\
&= \sum_{x\in B_{\delta}^c}f(\vec{x}|\hat{\theta}) + 2\sum_{x\in B_{\delta}}f(\vec{x}|\hat{\theta}) \\
&=  \sum_{x\in \mathscr X} f(\vec{x}|\hat{\theta}) + \sum_{x\in B_{\delta}}f(\vec{x}|\hat{\theta}) \\
&= 1+\sum_{x\in B_{\delta}}f(\vec{x}|\hat{\theta}) \underset {\theta >0}> 1 = R(\delta_{0}, \hat{ \theta})
\end{align}
$$
So we have found a $\theta\in \Theta$ where every rule is R-worse than $\delta_{0}$.
# Problem 3.3
**a)**
$$
\begin{align}
\Theta &= H_{0} \cup H_{1} = \mathbb{R}_{+} \\
\mathscr X &= \mathbb{R}^n \\
D &= \{\delta: \mathscr X \to \{0,1\}\} \\
L &= \text{0-1 loss}
\end{align}
$$
Because $\sigma$ is given, we can assume, that the parameter space is just the space of $\mu$.
**b)**
Do we need to show this?
Assuming iid we can say (because any linear combination of normally distributed random variables is also normal):
$$
\bar{X}_{n} = \frac{1}{n}\sum_{i=1}^nX_{i}\sim \mathcal N\left( \mu, \frac{\sigma^2}{n} \right)
$$
Likewise we can say:
$$
\bar{X}_{n}-\mu \sim \mathcal N\left( 0, \frac{\sigma^2}{n} \right)
$$
And finally:
$$
Z_{n} = \frac{(\bar{X}_{n}-\mu)\sqrt{ n}}{\sigma} \sim \mathcal N(0,1)
$$
Because:
$$
\begin{align}
Var(Z_{n}) &= Var \left( \frac{\sqrt{ n }}{\sigma} (\bar{X}_{n}-\mu)\right)  \\
&= \frac{n}{\sigma^2}Var(\bar{X}_{n}-\mu) \\
&= \frac{n}{\sigma^2}Var(\bar{X}_{n}) \\
&= \frac{n}{\sigma^2}\cdot \frac{\sigma^2}{n} = 1 \\
\end{align}
$$
since we know, that $\sigma^2 = 4$ we can now make the statement:
$$
\begin{align}
P\left( Z_{n} \geq q_{0.975} \right) &= 2.5\% \\
\Longleftrightarrow \hspace{1em} P\left( Z_{n} \geq 1.96 \right) &= 2.5\% \\
\Longleftrightarrow \hspace{1em} P \left(  \frac{(\bar{X}_{n}-\mu)\sqrt{ n}}{2} \geq 1.96\right) &= 2.5\% \\
\Longleftrightarrow \hspace{1em} P_{H_{0}} \left( \frac{\bar{X}_{n}\sqrt{ n }}{2} \geq 1.96 \right) &= 2.5\%
\end{align}
$$
Because this exactly equivalent to the critical region $C_{n}$ of our test we have now computed the probability for a type 1 error, i.e. the significance level. This means, that the significance level of the test is equal to 2.5%.
**c)**
We are looking the solution to the following term:
$$
P_{H_{1}}(t(\vec{X})\geq 1.96) =1-P_{H_{1}}\left(\frac{\bar{X}_{n}\sqrt{ n }}{2} < 1.96\right) 
$$
Meaning the test statistic realizes a value outside of the critical region under the alternative.
Under the alternative the term has the distribution:
$$
t(\vec{X}) \sim \mathcal N(\mu, 1)
$$
meaning that we can describe the probability of a type 2 error like so:
$$
1-\Phi \left( t(\vec{X})-\frac{\mu \sqrt{ n }}{2} \right) 
$$
So the power is dependent on the size of $\mu$. The higher $\mu$ the higher the power.
**d)**
$$
\begin{align}
\lambda(\vec{X}) &= \frac{\mathcal L(\vec{X}, 0)}{\sup_{\mu\in (0,\infty)}\mathcal L(\vec{X}, \mu)} \\
&= \frac{\left[ \frac{1}{\sqrt{ 2\pi }\sigma} \right]^n} {\left[ \frac{1}{\sqrt{ 2\pi }\sigma} \right]^n} \exp \left( \frac{1}{2 \sigma ^2}\sum_{i=1}^n x_{i}^2 - \frac{1}{2 \sigma ^2}\sum_{i=1}^n (x_{i}-\bar{x}_{n}) ^2 \right)  \\
&= \exp \left( 2\sum_{i=1}^nx_{i}\bar{x}_{n} - n  \right) 

\end{align}
$$

**e)**
Question: is the likelihood ratio montonic?
**f)**
We can express the risk depending on weither $H_{0}$ is true, or the alternative:
$$
R(t, \mu) = \begin{cases}
2.5\% &\text{if } \mu=0 \\
1-\Phi \left( t(\vec{X})-\frac{\mu \sqrt{ n }}{2} \right) & \text{else} 
\end{cases}
$$
and yes the function is piecewise monotonic, because it jumps to 97,5% at $\mu\to 0$ and then decreases. For $\mu = 0$ it is a single value.
