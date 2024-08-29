# Problem 3.4
using Bayes rule:
$$
f(\theta|x) \propto  f(x|\theta)g(\theta)
$$
Same with the whole sample:
$$
\begin{align}
\mathcal L(\theta|X) &\propto g(\theta)\prod_{i=1}^n f(x_{i}|\theta) \\
&= \frac{\beta^\alpha}{\Gamma(\alpha)}\theta^{\alpha-1}\exp(-\beta \theta) \theta^n\exp \left( -\theta \sum_{i=1}^n x_{i} \right)   \\
&= \frac{\beta^\alpha}{\Gamma(\alpha)}\theta^{\alpha-1+n}\exp \left( -\left( \beta+\sum_{i=1}^n x_{i} \right)  \theta \right) 
\end{align}
$$
So functionally it's a gamma distribution:
$$
\theta|X \sim \text{Gamma}\left( \alpha+n, \beta+\sum_{i=1}^nx_{i} \right)
$$
**b)**
$$
\begin{align}
\mathbb{E}((\theta-\delta(x))^2) &= \mathbb{E}(\theta^2-2\theta \delta(x)+\delta(x)^2) \\
&= \theta^2-2\theta \mathbb{E}(\delta(x))+\mathbb{E}(\delta(x)^2)
\end{align}
$$
On starting on the other side:
$$
\begin{align}
Var(\delta(x))+(\mathbb{E}(\delta(x))-\theta ^2) ^2&= \mathbb{E}(\delta(x)^2)-\mathbb{E}(\delta(x))^2+(\mathbb{E}(\delta(x))-\theta)^2 \\
&= \mathbb{E}(\delta(x)^2)-\mathbb{E}(\delta(x))^2+\mathbb{E}(\delta(x))^2-2\theta \mathbb{E}(\delta(x))-\theta ^2 \\
&= \mathbb{E}(\delta(x)^2)-2\theta \mathbb{E}(\delta(x)) -\theta ^2
\end{align}
$$
Which is the same as above, showing equality.
**c)**
The conditional mean will always minimize the Bayes risk under quadratic loss:
$$
\implies \delta_{g}(X) = \frac{\alpha+n}{\beta + \sum_{i=1}^n x_{i}}
$$
**d)**
Yes, the rule is unique, because there is just one solution.

Only admissible, if $R(\theta,\delta_{g})$ is continuous on $\Theta$

# Problem 3.5
**a)**
$$
\begin{align}
\Theta &= [0,1] \\
\mathscr X &= \{0,\dots,k\}^n = \{0,\dots,k\} \\
D &= \{\delta: \mathscr X \to [0,1]\} \\
L(\theta, \delta) &= \frac{(\theta-d)^2}{\theta(1-\theta)}
\end{align}
$$
**b)**
$$
\begin{align}  
f(\theta|X) &\propto f(X|\theta)g(\theta) \\
&= f(X|\theta)
\end{align}
$$
So posterior = likelihood
**c)**
First we define the Bayes risk:
$$
\begin{align}
B(\delta, \pi) &= \int_{\mathbb{R}_{+}} R(\delta,\theta)\pi(\theta)d\theta \\
&= \int_{0}^1 R(\delta,\theta)d\theta \\
&= \int_{0}^1\sum_{i=0}^kL(\delta,\theta)P(X_{1}=i)d\theta \\
&= \int_{0}^1 \sum_{i=0}^k\frac{((\theta-\delta)^2)}{\theta(1-\theta)} \binom{k}{i}\theta^i(1-\theta)^{k-i} d\theta
\end{align}
$$
From this follows the first order condition:
$$
\begin{align}
0&= B'(\delta, \pi)  \\
&= \int_{0}^1 \frac{1}{\theta(1-\theta)}\sum_{i=0}^k 2(\theta-\delta)P(X_{1} =i)d\theta
\end{align}
$$
**d)**
Is $\delta_{B} = \frac{X_{1}}{k}$ an equalizer rule?
$$
L(\delta_{B}, \theta) = \frac{\left( \frac{X_{1}}{k} -\theta\right)^2}{\theta(1-\theta)} 
$$
# Problem 3.6
**a)**
$$
\begin{align}
\Theta &= \{0,1\} \\
\mathscr X &= \mathbb{R}^n \\
D &= \{\delta:\mathscr X \to \{0,1\}\} \\
L &= \text{0-1 loss}
\end{align}
$$
**b)**
we have a linear combination of normal r.v. this means, that it's normal and we only have to find the mean and the variance:
$$
\begin{align}
\mathbb{E}(T) &= \frac{\mu}{\sqrt{ \frac{8}{n} }}   \\
&= \frac{\mu}{\sqrt{ \frac{\sigma^2}{2n} }} \\
Var(T) &= \frac{\frac{4}{n ^2}}{\frac{8}{n}} \sum_{i=1}^{n/2}Var(X_{i}) \\
&= \frac{32}{n^3} \sum_{i=1}^{n/2}\sigma^2 \\
&= \frac{16}{n ^2} \sigma ^2 = \frac{16^2}{16^2} = 1 \\
\end{align}
$$
So:
$$
T\sim \mathcal N\left( \frac{\mu}{\sqrt{ \frac{\sigma^2}{2n} }}, 1 \right) 
$$
And under $H_{0}$ it is standard normal.
**c)**
$$
\alpha = P_{H_{0}}(T \leq -1.645) = \Phi(-1.645) = 1-\Phi(1.645) = 5\%
$$
so significance level is 5%
**d)**
$$
\lambda(X) = \frac{\mathcal L(X|0)}{\max_{\mu\in \mathbb{R}}\mathcal L(X|\mu)}
$$
The ML estimator for $\mu$ is the sample mean $\bar{x}_{n}$.
Now inserting this:
$$
\begin{align}
\lambda(X) &= \frac{\prod_{i=1}^n f(x_{i}|0, 4)}{\prod_{i=1}^nf(x_{i}|\bar{X}_{n}, 4)} \\
&= \frac{\exp\left( -\frac{1}{2\sigma ^2} \sum_{i=1}^n x_{i}^2\right)}{\exp\left( -\frac{1}{2\sigma^2}\sum_{i=1}^n(x_{i}-\bar{x}_{n})^2 \right)}
\end{align}
$$