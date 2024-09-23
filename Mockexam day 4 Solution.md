# Problem 1.1
**a)**
Let $\epsilon >0$. In that case we can say:
$$
\begin{align}
P(|X_{n}|>\epsilon) &= P(|X_{n}-\mathbb{E}(X_{n})|> \epsilon)\\
&\leq \frac{Var(X_{n})}{\epsilon^2} \\
&= \frac{\frac{\left(2\frac{1}{n}  \right)^2 }{12}}{\epsilon^2} \\
&= \frac{4}{12} \frac{1}{n^2} \frac{1}{\epsilon^2} \to 0
\end{align}
$$
Showing, that $X_{n}$ converges in prob. to 0 
**b)**
The cdf of $X_{n}$ is:
$$
F_{X_{n}}(x) = \begin{cases} 
0  &x < -\frac{1}{n} \\
\frac{n}{2}\left( x+\frac{1}{n} \right) & x\in \left[ -\frac{1}{n}, \frac{1}{n} \right] \\
1 &x > \frac{1}{n}
\end{cases}
$$
And for 0 it is:
$$
F_{0}(x) = 1_{x\geq 0}(x)
$$
It holds that:
$$
F_{X_{n}} \to F_{X}(x) = \begin{cases}
0 &x<0 \\
\frac{1}{2} &x =0 \\
1 & x>0
\end{cases}
$$
Meaning pointwise convergence holds for all continuity points of $F_{0}$ and therefore convergence in distribution holds
**c)**
Starting with $\implies$: This is already generally given. 
And with $\Longleftarrow$ :
Given $X_{n}\to a$ in distribution, let $\epsilon>0$, then we can say that:
$$
\begin{align}
P(|X_{n}-a|\leq \epsilon) &= P(-\epsilon\leq X_{n}-a\leq\epsilon) \\
&= P(a-\epsilon\leq X_{n}\leq\epsilon+a) \\
&= F_{X_{n}}(a+\epsilon)-F_{X_{n}}(a-\epsilon) \\
&\to 1-0 = 1
\end{align}
$$
And because of that we can say that:
$$
P(|X_{n}-a|>\epsilon) = 1-P(|X_{n}-a|\leq \epsilon)\to 1-1 = 0
$$
**d)**
Strong law of large numbers now implies that:
$$
\bar{X}_{n}\to \mu \hspace{1em} \text{a.s.}
$$
Then this implies:
$$
\bar{X}_{n} \overset p \to \mu
$$
But then CMT says that:
$$
g(\bar{X}_{n})\to g(\mu)
$$
For any continuous function. If we now say that $g(x) = x^2$ we showed the statement.

# P. 1.2
**a)** Let $\omega \in \Omega$ then it holds that:
$$
X_{n}(\omega)= \frac{\omega}{n}\to 0
$$
So:
$$
P(\{\omega\in \Omega|X_{n}(\omega)\to 0\}) = P(\Omega)= 1
$$
**b)**
Since for any $\omega\in \mathbb Q\cap[0,1]$:
$$
Y_{n}(\omega) = \omega \ln(n) \to \infty
$$
So the function certainly does not converge for those points. But since:
$$
\begin{align}
P(Y_{n} = 0) &= \lambda([0,1] \setminus \mathbb Q) \\
&= \lambda([0,1])-\lambda(\mathbb Q \cap [0,1]) \\
&= 1 -0 = 1
\end{align}
$$
The property of convergence almost surely holds for any element of the sequence and therefore also for the limit. 
**c)**
We have shown $X_{n}\to 0$ in a) and this also implies $X_{n} \overset p\longrightarrow 0$ and therefore also CMT applies. And we can define $g(X_{n}) = X_{n}^2=Z_{n}$ and thus it holds that:
$$
Z_{n} \overset p\longrightarrow 0
$$
# P. 1.3
**a)**
The function of interest is $g(x) = x^2$ meaning $g'(x) = 2x$ and thus:
$$
\sqrt{ n }\left( \bar{X}_{n} ^2-\mu^2 \right)\overset p\longrightarrow \mathcal N(0, 4\mu^2\sigma^2) 
$$

**b)**
Same here but $g(x) = \ln(x)$ so $g'(x) = \frac{1}{x}$ and:
$$
\sqrt{ n }(\ln\bar{X}_{n}-\ln \mu) \to \mathcal N\left( 0, \frac{\sigma^2}{\mu^2} \right)
$$
But this is not defined for $\mu=0$.

# P 2.1
**a)**
Likelihood:
$$
\begin{align}
\mathcal L(\vec{X}|\theta) &= \prod_{i=1}^n f(x_{i}|\theta) \\
&= \prod_{i=1}^n \frac{1}{\theta} \\
&=  \frac{1}{\theta^n}
\end{align}
$$
Mon. decreasing in $\theta$. So the smallest value possible, we therefore choose $\hat{\theta} = \max\{x_{1},\dots,x_{n}\}$.
**b)**
$$
F_{X_{1}} = \begin{cases}
0 &x<0 \\
\frac{1}{\theta}x &x\in[0,\theta] \\
1 & x>\theta
\end{cases}
$$
**c)**
Using the hint the cdf is:
$$
F_{\hat{\theta}_{ML}}(x) = F_{X_{1}}(x)^n=\begin{cases} 
0 &x<0 \\
\frac{1}{\theta^n}x^n &x\in[0,\theta] \\
1 &x>\theta
\end{cases}
$$
**d)**
Using the result from **c)**, we can get the density:
$$
f_{\hat{\theta}_{ML}}(x) = \frac{n}{\theta^n}x^{n-1}1_{[0,\theta]}(x)
$$
And following this the risk breaks down into bias and variance. So:
$$
\begin{align}
R(\hat \theta_{ML}, \theta) &= \mathbb{E}(\hat{\theta}_{ML}^2)-\mathbb{E}(\hat{\theta}_{ML})^2+(\mathbb{E}(\hat{\theta}_{ML})-\theta)^2
\end{align}
$$
So we need $\mathbb{E}(\hat{\theta}_{ML})$ and $\mathbb{E}(\hat{\theta}_{ML}^2)$
$$
\begin{align}
\mathbb{E}(\hat{\theta}_{ML}) &= \int_{\mathbb{R}} x\frac{n}{\theta^n}x^{n-1}1_{[0,\theta]}(x)dx \\
&= \int_{0}^\theta   \frac{n}{\theta^n}x^ndx \\
&= \frac{n}{\theta^n}\left[ \frac{1}{n+1}x^{n+1} \right]_{0}^\theta \\
&= \frac{n}{n+1}\theta
\end{align}
$$
As well as:
$$
\begin{align}
\mathbb{E}(\hat{\theta}_{ML}^2) &= \int_{\mathbb{R}}x^2   \frac{n}{\theta^n}x^{n-1}1_{[0,\theta]}(x)dx \\
&= \int_{0}^\theta   \frac{n}{\theta^n}x^{n+1}dx \\
&= \frac{n}{\theta^n} \left[ \frac{1}{n+2}x^{n+2} \right]_{0}^\theta \\
&= \frac{n}{n+2}\theta^2 
\end{align}
$$
And therefore we get for the risk:
$$
\begin{align}
R(\hat{\theta}_{ML},\theta) &= \frac{n}{n+2}\theta^2 -\frac{n^2}{(n+1)^2}\theta^2+ \left[ \frac{n}{n+1}\theta-\theta \right]^2 \\
&= \frac{n}{n+2}\theta^2-\frac{n^2}{(n+1)^2}\theta^2+\frac{1}{(n+1)^2}\theta^2 
\end{align}
$$
Asymptotically we need to use L'Hospital:
$$
\begin{align}
\lim_{ n \to \infty } \frac{n^2}{(n+1)^2} &= \lim_{ n \to \infty } \frac{2n}{2(n+1)} \\
&= \lim_{ n \to \infty }   \frac{2}{2} = 1
\end{align}
$$
Then we get:
$$
\lim_{ n \to \infty } R(\hat{\theta}_{ML}, \theta) = \theta^2-\theta^2+0 = 0
$$
# Problem 2.2
**a)**
The UMP test provides the biggest power for a given size
So for $\alpha > 0$:
$$
P_{\theta}(\vec{X}\in C_{\delta_{UMP}}) \geq P(\vec{X}\in C_{\delta}) \hspace{1em} \forall \theta\in \Theta_{0}, \delta\in\mathcal D
$$
**b)**
So UMP according to Neyman Pearson is:
$$
\begin{align}
LQ &=\frac{ \mathcal L(\vec{x}|\theta_{0})}{\mathcal L(\vec{x}|\theta_{1})} \leq k ; \hspace{1em} x\in C\\
&\Longleftrightarrow \frac{\prod_{i=1}^n\theta_{0}\exp(-\theta_{0}x_{i})}{\prod_{i=1}^n \theta_{1}\exp(-\theta_{1}x_{i})} \leq k \hspace{1em} x\in C\\
&\Longleftrightarrow\frac{\theta_{0}^n}{\theta_{1}^n} \exp\left( -(\theta_{0}-\theta_{1})\sum_{i=1}^nx_{i} \right) \leq k \hspace{1em} x\in C \\
&\Longleftrightarrow \sum_{i=1}^n x_{i} \geq \frac{1}{(\theta_{0}-\theta_{1})} \ln \left(  \left( \frac{\theta_{1}}{\theta_{0}} \right)^nk \right) 
\end{align}
$$

# Problem 2.3
NP lemma with binary case:
![[Pasted image 20240904215235.png]]
