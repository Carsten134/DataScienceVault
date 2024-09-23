**a)**
We first compute the likelihood function:
$$
\begin{align}
\mathcal L(X|\theta) &= \prod_{i=1}^nf(x_{i}, \theta) \\
&= \prod_{i=1}^n \frac{x_{i}}{\theta ^2}\exp\left( -\frac{x_{i}}{\theta} \right) \\
&= \frac{1}{\theta^{2n}} \exp\left( -\frac{1}{\theta}\sum_{i=1}^n x_{i} \right)\prod_{i=1}^n x_{i}
\end{align}
$$
Then compute the log likelihood:
$$
\begin{align}
\ln \mathcal L(X|\theta) &= -2n \ln(\theta)-\frac{1}{\theta}\sum_{i=1}^n x_{i}+ \sum_{i=1}^n \ln(x_{i})
\end{align}
$$
Then FOC:
$$
\begin{align}
\ln \mathcal L'(X|\theta) &= -\frac{2n}{\theta}+\frac{1}{\theta^2}\sum_{i=1}^nx_{i} =0 \\
-2n +\frac{1}{\theta}\sum_{i=1}^n x_{i} &= 0 \\
\frac{1}{\theta} \sum_{i=1}^nx_{i} &= 2n \\
\frac{1}{2n}\sum_{i=1}^n x_{i} &= \theta
\end{align}
$$
**b)**
We already have been given the lower boundary:
$$
\frac{1}{n\mathbb{E}\left[ \left( \frac{\partial}{\partial \theta}l(X;\theta) \right)^2  \right] }
$$
So let's first derive the score:
$$
\begin{align}
\frac{\partial}{\partial \theta} l(x;\theta) &= \frac{\partial}{\partial \theta} \ln \left(   \frac{x}{\theta^2} \exp\left( -\frac{x}{\theta} \right)  \right)\\
&= \frac{\partial}{\partial \theta}\ln x -2\ln \theta -\frac{x}{\theta} \\
&= -\frac{2}{\theta}+\frac{x}{\theta^2}
\end{align}
$$
second derivative:
$$
\frac{2}{\theta^2}-\frac{2x}{\theta^3}
$$
And apply the mean:
$$
\begin{align}
-\mathbb{E}\left( \frac{2}{\theta^2}-\frac{2X}{\theta^3} \right) &= -\frac{2}{\theta ^2}+\frac{2}{\theta^3}2\theta \\
&= - \frac{2}{\theta^2}+\frac{4}{\theta^2} \\
&= \frac{2}{\theta ^2}
\end{align}
$$
So we get the lower bound:
$$
Var(T) \geq \frac{1}{\frac{2n}{\theta^2}} = \frac{\theta^2}{2 n}
$$
**c)**
Computing the variance of the maximum likelihood estimator:
$$
\begin{align}
Var(\hat{\theta}_{ML}) &= \frac{1}{4n^2}Var\left( \sum_{i=1}^n X_{i} \right) \\
&= \frac{1}{4n^2} \sum_{i=1}^n Var(X_{i}) \\
&= \frac{1}{4n^2}\sum_{i=1}^n 6 \theta^2-4 \theta^2 \\
&= \frac{1}{4n^2}n 2\theta^2 \\
&= \frac{\theta ^2}{2n}
\end{align}
$$
So the lower bound is reached but is the estimator unbiased?
$$
\begin{align}
\mathbb{E}(\hat{\theta}_{ML}) &= \frac{1}{2n}\sum_{i=1}^n\mathbb{E}(X_{i}) \\
&= \frac{2n}{2n}\theta = \theta
\end{align}
$$
So yes and it is admissible because of bias variance decomposition.
**d)**
Bias variance decomposition:
$$
\begin{align}
Var(\hat{\theta}_{2}) &= \frac{1}{4(n+1)^2}\sum_{i=1}^nVar(X_{i}) \\
&= \frac{n 6\theta^2}{4(n+1)^2}
\end{align}
$$
And the bias:
$$
\begin{align}
\mathbb{E}(\hat{\theta}_{2}) &= \frac{1}{2(n+1)}\sum_{i=1}^n \mathbb{E}(X_{i})  \\
&=\frac{n}{n+1}\theta \\
\text{Bias}(\hat{\theta}_{2})^2 &= \frac{\theta^2}{(n+1)^2} \\
\end{align}
$$
Comming to the risk:
$$
\begin{align}
R(\hat{\theta}_{2}, \theta) &= \frac{6n \theta^2}{4(n+1)^2} + \frac{\theta^2}{(n+1)^2} \\
&= \frac{(6n-4)\theta^2}{4(n+1)^2} \leq \frac{\theta^2}{2n} \forall n>0
\end{align}
$$
# Problem 3.11
**a)**
$$
\begin{align}
R(\delta_{a,b}, \mu) &= \mathbb{E}((\mu-a-bX)^2) \\
&= Var(\delta_{a,b})+ \text{Bias}(\delta_{a,b})^2 \\
&= b^2+(a+b\mu-\mu)^2 \\
&= b^2+(a+(b-1)\mu)^2
\end{align}
$$
**b)**
Inserting into the formula from a)
$$
\begin{align}
R(\delta_{a,b},\mu) &= 1
\end{align}
$$
**c)**
No because the risk increases in $b$

# Problem 3.12
