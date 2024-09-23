# Problem 2.1
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
# Problem 2.2
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

# Problem 2.3
**a)**
NP-lemma is applied and we look at the likelihood ratio:
$$
\begin{align}
LQ = \frac{\mathcal L(\vec{X}|p_{1})}{\mathcal L(\vec{X}|p_{0})} &>k \hspace{1em} \forall x\in C\\
\frac{ \prod_{i=1}^{10} p^{x_{i}}_{1} (1-p_{1})^{1-x_{i}} }{\prod_{i=1}^{10}p_{0}^{x_{i}}(1-p_{0})^{1-x_{i}}} &>k \hspace{1em} \forall x\in C\\
\frac{\left( p_{1}^{\sum_{i=1}^{10}x_{i}}(1-p_{1})^{10-\sum_{i=1}^{10}x_{i}} \right)}{\left( p_{0}^{\sum_{i=1}^{10}x_{i}}(1-p_{0})^{10-\sum_{i=1}^{10}x_{i}} \right)} &> k \hspace{1em} \forall x\in C \\
\left( \frac{p_{1}}{p_{0}} \right)^{\sum_{i=1}^{10}x_{i}}\left( \frac{1-p_{1}}{1-p_{0}} \right)^{10-\sum_{i=1}^{10}x_{i}}&> k\hspace{1em} \forall x\in C \\
\left( \frac{p_{1}}{p_{0}} \frac{1-p_{0}}{1-p_{1}} \right)^{\sum_{i=1}^{10}x_{i}}&> k \left( \frac{1-p_{0}}{1-p_{1}} \right)^{10}     \hspace{1em}\forall x\in C\\
\sum_{i=1}^{10} x_{i} &< k^* \hspace{1em}\forall x\in C
\end{align}\hspace{1em} 
$$
Because $\log_{a}(x)$ is a decreasing function for all $a<1$, the inequality shifts in the other direction.

**b)**
The size is (in this case) the probability of making a type 1 error:
$$
\begin{align}
\alpha &= P(\vec{X}\in C) \\
&= P_{p_{0}}\left(  \sum_{i=1}^{10} x_{i} \leq c_{r}-1 \right)+ P_{p_{0}}\left( \sum_{i=1}^{10} x_{i} = c_{r} \right)\gamma
\end{align}
$$
we can choose $c_{r} = 6$, then:
$$
P\left( \sum_{i=1}^{10} x_{i} \leq c_{r}-1 \right) = P\left( \sum_{i=1}^{10} x_{i} \leq 5 \right) = 0.150
$$
And choose $\gamma$ such that:
$$
\begin{align}
P\left( \sum_{i=1}^{10} x_{i} = 6 \right)\gamma &= \alpha - P\left( \sum_{i=1}^{10}x _{i}\leq 5 \right) \\
0.2\gamma &= 0.2-0.15  \\
\frac{1}{5} \gamma &= 5 \% \\
\implies \gamma &= 5*5\% = 25\% 
\end{align}
$$

**c)**
Assuming 0-1 loss we can say:
$$
\begin{align}
R(\phi, p) &= \begin{cases}
P_{p_{0}}(\vec{X}\in C)  & p=p_{0} \\
P_{p_{1}}(\vec{X}\not\in C) &p=p_{1}
\end{cases} \\
&= \begin{cases}
P_{p_{0}}\left( \sum_{i=1}^{10}x_{i} \leq 6 \right)+0.56\cdot P_{p_{0}}\left( \sum_{i=1}^{10} x_{i} = 7 \right) & p=0.7 \\
P_{p_{1}}\left( \sum_{i=1}^{10} x_{i} \geq 8 \right) &p=0.3
\end{cases} \\
&= \begin{cases}
\approx 0.5 & p=0.7 \\
\approx 0 & p=0.3
\end{cases}
\end{align}
$$
No this is not minimax, because the risk is not invariant of $p$.