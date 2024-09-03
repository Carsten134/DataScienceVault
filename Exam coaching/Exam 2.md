**a)**
Exponential form for one parameter exponential densities:
$$
f_{X}(x|\theta) = \exp(\eta(\theta)T(x)-A(\theta)+B(x))
$$
Applying this to the given density:
$$
\begin{align}
f(x;\theta) &= \theta(1+x)^{-(\theta+1)} \\
&= \exp(\ln(\theta)-(\theta+1)\ln(1+x))
\end{align}
$$
This leads to:
$$
\begin{align}
A(\theta)& = -\ln(\theta) \\
\eta(\theta) &= -(\theta+1) \\
T(x) &= \ln(1+x)
\end{align}
$$
**b)**
Using Bayes rule
$$
\begin{align}
f(\theta|X) &\propto \mathcal L(X|\theta)g(\theta) \\
&= g(\theta)\prod_{i=1}^nf(x_{i}|\theta) \\
&= \exp(-p\theta) \prod_{i=1}^n\theta(1+x_{i})^{-(\theta+1)} \\
&= \exp(-p\theta)\theta^n\prod_{i=1}^n(1+x_{i})^{-(\theta+1)} \\
&= \exp(-p\theta)\theta^n\exp\left( -(\theta+1)\sum_{i=1}^n \ln(1+x_{i}) \right) \\
&\propto \theta^n\exp\left( -\theta\left( p+ \sum_{i=1}^n \ln(1+x_{i}) \right) \right)
\end{align}
$$
So it's Gamma with the parameters:
$$
\theta|X\sim \text{Gamma}\left( n-1, p+\sum_{i=1}^n \ln(1+x_{i}) \right)
$$
**c)**
Well $g(\theta)$ is a kernel of the exponential distribution and would need some proper scaling:
$$
f_{g}(\theta) = p \exp(-p\theta)
$$
So no it's no proper prior because:
$$
\int_{\mathbb{R}_{+}}g(\theta)d\theta \neq 1
$$
But because we look at just the kernel for the posterior as well, it does not make a difference, because the scaling drops out anyways.
**d)**
Because we have quadratic loss we already know that the solution to the bayes rule is the posterior expected value:
$$
\begin{align}
\arg \min_{\delta\in\mathcal D}B(\delta, g) &= \mathbb{E}(\theta|X) \\
&= \frac{n-1}{p+ \sum_{i=1}^n \ln(1+x_{i})}
\end{align}$$
**e)**
For this we need to compute the likelihood:
$$
\begin{align}
\mathcal L(X|\theta) &= \prod_{i=1}^n f(x_{i}|\theta) \\
&= \prod_{i=1}^n \theta(1+x_{i})^{-(\theta+1)} \\
&= \theta ^n\exp\left( -(\theta+1)\sum_{i=1}^n \ln(1+x_{i}) \right)
\end{align}
$$
log scale the likelihood:
$$
\begin{align}
\ln \mathcal L(X|\theta) &= n \ln \theta -(1+\theta) \sum_{i=1}^n \ln(1+x_{i}) \\
\implies \text{FOC}: \ln\mathcal L'(X|\theta) &= \frac{n}{\theta}-\sum_{i=1}^n\ln(1+x_{i}) =0 \\
\hat{\theta}_{ML} &= \frac{n}{\sum_{i=1}^n \ln(1+x_{i})}
\end{align}
$$
This is different from the Bayes-rule because we are not utilizing the information from the prior. The higher $p$ the more smaller values are more common and therefore the estimation is biased downwards.

# Problem 3.14
**a)**
$$
\begin{align}
R(\delta, \theta) &= Var(\delta)+\text{Bias}(\delta) ^2 \\
&= a^2Var(X) + \left( \mathbb{E}(aX+b)-\theta \right)^2 \\
&= a^2(n\theta(1-\theta)) + \left( an\theta+b-\theta\right)^2 \\
&= a^2n\theta(1-\theta)+ ((an-1)\theta+b)^2 \\
&= a^2n\theta - a^2n\theta^2+(an-1)^2\theta^2 -2(an-1)\theta b+b^2 \\
&= ((an-1)^2-a^2n)\theta^2+(a ^2n-2b(an-1))\theta+ b ^2  
\end{align}
$$
So this leads to the definitions:
$$
\begin{align}
\alpha &= (an-1)^2-a^2n \\
\beta &= a^2n-2b(an-1) \\
\gamma &= b^2 
\end{align}
$$
**b)** 
So using the hint we get the condition:
$$
R'(\delta_{a,b},\theta) = 2\alpha \theta+\beta = 0
$$
This means that (because $\theta \neq 0$ is possible):
$$
\begin{align}
\alpha &= 0 \\
\beta &= 0 \\
\end{align}
$$
So inserting this into the definitions of $\alpha$ and $\beta$:
$$
\begin{align}
(an-1)^2-a^2n &= 0 \\
a^2n -2b(an-1) &= 0 \\
\implies an-1 &= a \sqrt{ n } \\
a(n-\sqrt{ n })& = 1 \\
a_{M} &= \frac{1}{n-\sqrt{ n }} \\
\implies a ^2n &=2b(an-1)  \\
\frac{n}{(n-\sqrt{ n })^2} &= 2b\left( \frac{\sqrt{ n }}{n-\sqrt{ n }} \right) \\
\frac{\sqrt{ n }}{2(n-\sqrt{ n })} &= b_{M}
\end{align}
$$


And this means, that the risk is constant at:
$$
\begin{align}
R(\delta_{\alpha_{M},\beta_{M}},\theta) &= \frac{n}{4(n-\sqrt{ n })^2}
\end{align}
$$
# Problem 3.15
**a)**
To find the cdf we need to find the antiderivative of the pdf:
$$
F(x;\theta) = \begin{cases}
0 &x\leq 0 \\
x^\theta & x\in (0,1) \\
1 &\text{else}
\end{cases}
$$
The cdf for the sample maximum is therefore, following the formula:
$$
\begin{align}
F_{X_{[n]}}(x) = F_{X}(x)^n
\end{align}
$$
And therefore we get:
$$
F_{X_{[n]}}(x;\theta) = \begin{cases}
0 &x\leq 0 \\
x^{n\theta} & x\in(0,1) \\
1 &\text{else}
\end{cases}
$$
**b)**
$$
\begin{align}
\alpha &= P_{H_{0}}(\vec{x}\in C_{n}) \\
&= 1-P(x_{[n]}< 0.90^{3/n}) \\
&= 1-(0.90^{3/n})^{n/3} \\
&= 1-0.9 = 0.1
\end{align}
$$
So the size is $10\%$.
**c)**
It holds trivially that:
$$
X_{[n]} \overset d\to Y
$$
Where:
$$
P(Y = 1) = 1
$$
And it holds that:
$$
0.9^{3/n} \to 1
$$
So asymptotically we get:
$$
C_{n}\to C =\{\vec{x}:x_{[n]}\geq 1\}
$$
And the size:
$$
\begin{align}
\alpha &= P_{H_{0}}(Y\in C) \\
&= 1-P(Y<1) =1-0 =1
\end{align}
$$
But it should converge to 0 so no, it's not consistent
**d)**
![[Pasted image 20240830164109.png]]
