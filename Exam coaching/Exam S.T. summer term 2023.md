# Probability Theory
## Problem 1.1
**a)**
Let $\Omega$ be a sample space and $\mathcal A$ a $\sigma$-Algebra on that sample space. Then the mapping $P: \mathcal{A}\to [0,1]$  is a probability measure iff:
1. $P(A) \geq 0 \forall A\in \mathcal{A}$
2. $P(\Omega) = 1$
3. $P\left( \biguplus_{i=1}^\infty A_{i}  \right) = \sum_{i=1}^\infty P(A_{i})$
**b)**
$$
\begin{align}
\sigma(\mathcal E) &= \{\emptyset, \Omega, \{1\}, \{2,3,4\}, \{4\}, \{1,2,3\}, \{1,4\}, \{2,3\}\} \\
\mathcal P(\Omega) &= \{\emptyset, \Omega, \{1\}, \{2,3,4\}, \{4\}, \{1,2,3\}, \{1,4\}, \{2,3\}, \{1,3\},\{1,2\}, \\
& \{2,4\}, \{3,4\}, \{1,3,4\}, \{1,2,4\}, \{2\},\{3\}\}
\end{align}
$$
**c)**
So we have been given:
$$
P(A) = Q(A) = c \hspace{1em} \forall A\in \mathcal E
$$
But also because of the property of probability measures:
$$
P(A^c) = Q(A^c) = 1-c \hspace{1em} \forall A\in\mathcal E
$$
This means, that (using Lemma 1.2): 
$$
P(\{1,4\}) = Q(\{1,4\}) = 2c
$$
And also:
$$
P(\{1,4\}^c) = Q(\{1,4\}^c) = 1-2c
$$
So that fully specifies all the sets and shows:
$$
P(A) = Q(A) \hspace{1em} \forall A\in \sigma(\mathcal E)
$$
**d)**
Counterexample with:
$$
P(A) = \delta_{2}(A)\hspace{1em} Q(A)= \delta_{3}(A)
$$
**e)**
$$
\begin{align}
\sum_{\omega\in \Omega}\omega P(\{\omega\}) &= 5c + 2a +3b
\end{align}
$$
With the side conditions of $2c + a +b = 1$ and $0\leq c<\frac{1}{2}$. This means $b=1$ is the right solution. 
## Problem 1.2
**a)**
We shown this, just wing the proof
**b)**
Here it is important to state, that the characteristic functions always exist, while the moment generating function can't always exist because the values can diverge.
**c)**

# Decision Theory
## Problem 2.1
**a)**
First let's compute the likelihood:
$$
\begin{align}
\mathcal L(X|\theta) &= \prod_{i=1}^n f(x_{i}|\theta) \\
&= \prod_{i=1}^n \frac{1}{\theta} \\
&= \frac{1}{\theta^n}
\end{align}
$$
So the likelihood is decreasing in $\theta$. Therefore we need to take the smallest $\theta$ where all of realizations are still in the support of the resulting density.
$$
\implies  \hat{\theta}_{ML} = \max_{i\in\{1,\dots,n\}}x_{i}
$$
**b)**
From the way the cdf is defined, we already know that the support of $f$ is the interval $[0,\theta)$ and there the pdf is just the derivative of the cdf:
$$
\implies f(x) := \begin{cases}
0 &,x<0 \\
\frac{n}{\theta}\left( \frac{x}{\theta} \right)^{n-1} &,0\leq x<\theta  \\
0, &\text{else} 
\end{cases}
$$

And for the expectation:
$$
\begin{align}
\mathbb{E}(\hat{\theta}_{ML}) &= \int_{0}^\theta x  \frac{n}{\theta}\left( \frac{x}{\theta} \right) ^{n-1} dx \\
&= \int_{0}^\theta n \left( \frac{x}{\theta} \right)^n dx \\
&= n \int_{0}^1 u^n \theta du \\
&= n \theta\left[ \frac{u^{n+1}}{n+1} \right]_{0}^1  \\
&= \theta  \frac{n}{n+1}
\end{align}
$$
So the estimator is biased but asymptotically unbiased. 
**c)**
We again are going to use bias variance decomposition:
$$
\begin{align}
\mathbb{E}((\theta-\tilde{\theta})^2) &= Var(\tilde{ \theta}) + Bias(\tilde{ \theta})^2 \\
&= \frac{(n+1)^2}{n ^2} \frac{n}{(n+2)(n+1)^2}\theta^2 + 0 \hspace{1em} \text{unbiased + hint} \\
&= \frac{1}{(n+2)n}\theta ^2
\end{align}
$$
For $\bar{ \theta}$ we are going to first show, that it is unbiased:
$$
\begin{align}
\mathbb{E}(\bar{ \theta}) &= 2 \frac{1}{n} \sum_{i=1}^n \mathbb{E}(X_{i}) \\
&= 2 \frac{1}{n} n \frac{\theta}{2} = \theta
\end{align}
$$
Then we continue with the loss:
$$
\begin{align}
\mathbb{E}((\theta-\bar{\theta})^2) &= Var(\bar{\theta}) \hspace{1em} \text{unbiased} \\
&= \frac{4}{n^2} Var \left( \sum_{i=1}^n X_{i} \right)  \\
&= \frac{4}{n^2} \sum_{i=1}^n Var(X_{i}) \\
&= \frac{4}{n^2} \sum_{i=1}^n \frac{\theta^2}{12} \\
&= \frac{4}{n ^2} n \frac{\theta^2}{12} \\
&= \frac{\theta^2}{3n}
\end{align}
$$
Now that we have these two risks we can compare them:
$$
\begin{align}
\frac{1}{(n+2)n}\theta^2 &\leq \frac{\theta^2}{3n} \\
\Longleftrightarrow \frac{1}{n+2} \leq    \frac{1}{3} \\
\Longleftrightarrow 1 \leq n
\end{align}
$$
This means, that the corrected maximum likelihood estimator is R-better.
## Problem 2.2
**a)**
The set is not **minimally** essentially complete, because the lower boundary is also essentially complete, we therefore have found a proper subset, that is essentially complete which proves the statement 
**b)**
Because the 45 degree line is also a proper subset and complete. Therefore proving, that the proposed set is only complete but not minimal
**c)**
The 45 degree line of the lower border is a minimally complete set, because all rules are admissible meaning, that there is no R-better rule in the decision set for every element of the proposed set of the half-circle
**d)**
No, because the set is convex. If you take two points (or rules) of the set, their line will be above the proposed line (so all the randomized rules are R-worse than the rules from the set)
**e)**
Because all the rules are admissible, we only need to find an equalizer rule:
$$
\begin{align}
R(\theta_{1}, \delta_{M}) &= R(\theta_{0}, \delta_{M}) \\
y &= 1-\sqrt{ 1-(y-1)^2} \\
1-y &=  \sqrt{ 1-(y-1)^2 } \\
(1-y)^2 &= 1-(y-1)^2 \\
(1-y)^2+(y-1)^2 &= 1 \\
1-2y+y ^2+y^2-2y +1 &= 1 \\
0 &= 2y^2-4y +1 \\
0&= y^2-2y + \frac{1}{2} \\
y_{1,2} &= 1 \pm \sqrt{ 1-\frac{1}{2}}  \\
y &= 1-\sqrt{ 0.5 }
\end{align}
$$
## Problem 2.3
**a)**
$$
\begin{align}
\Theta &= \{0.3, 0.7\} \\
\mathscr X &= \{0,1\}^2 \\
D &= \{\delta_{0}, \delta_{1}\} = \begin{cases}
H_{0} \text{ is true} \\
H_{1} \text{ is true}
\end{cases}\\
L &=  \text{0-1 loss}
\end{align}
$$

**b)**
We can say:
$$
Y \sim \text{Binom}(2, p)
$$
And this makes the calculation a lot easier:
$$
\begin{align}
P_{p_0}(Y = 0) &= (1-p_{0})^2 = 0.49 \\
P_{p_{0}}(Y=1) &= 2p_{0}(1-p_{0}) = 2*0.3*0.7 =  0.42 \\
P_{p_{0}}(Y = 2) &= p_{0}^2 = 0.3^2 = 0.09
\end{align}
$$
On the other hand for $p_{1} = 0.7$ we get:
$$
\begin{align}
P_{p_1}(Y = 0) &= (1-p_{1})^2 = 0.09 \\
P_{p_{1}}(Y=1) &= 2p_{1}(1-p_{1}) = 2*0.7*0.3 =  0.42 \\
P_{p_{1}}(Y = 2) &= p_{1}^2 = 0.7^2 = 0.49
\end{align}
$$
For the accept and reject probabilities we get:
$$
\begin{align}
P_{p_{0}}(\delta(Y,\{0.7\}) = 0) &=  P_{p_{0}}(Y\neq 2) = 0.91\\
P_{p_{0}}(\delta(Y,\{0.7\}) = 1) &= P_{p_{0}}(Y = 2) = 0.09 \\
P_{p_{1}}(\delta(Y,\{0.7\}) = 0) &= P_{p_{1}}(Y\neq 2) = 0.51  \\
P_{p_{1}}(\delta(Y,\{0.7\}) = 1) &= P_{p_{1}}(Y = 2) = 0.49
\end{align}
$$
So Type 1 (false rejection) is pretty low at 9% but false acceptance is even higher than correct acceptance at 49%.
**c)**
Like said in **b)** the test statistic is binomial distributed by definition:
$$
Y\sim\text{Binom}(2, p)
$$

And for any specific $\alpha$ for the size of the test, yes we can, by randomization:
$$
\delta_{\alpha}(y, \{0.7\}) = \begin{cases}
X \sim \text{Bernoulli}\left( \min\left\{ 1, \frac{0.09}{\alpha} \right\} \right)
 &, y = 2 \\
0&, \text{else}
\end{cases}
$$
**d)**
The risk is the expected loss:
$$
\mathbb{E}(L(\delta, p))
$$
With the $\text{0-}K_{i}$ loss we get:
$$
\begin{align}
\mathbb{E}(L(\delta(y,\{0.7\}, p))) &= \begin{cases}
P(\text{type 1 error}) 2K_{0} &, \text{ if } p = 0.3 \\
P(\text{type 2 error}) K_{0} &, \text{ if } p=0.7
\end{cases}
\end{align}
$$
**e)**
To calculate the Bayes risk we have to compute:
$$
B(\delta, P) =\sum_{i=0}^1R(\delta,p_{i})P(p=p_{i})
$$
Now $p$ is a random variable and now the computation changes to:
$$
\begin{align}
\sum_{i=0}^1 R(\delta,p_{i})P(p=p_{i}) &= P(p=p_{0})P(\text{type 1 error})2K_{0} \\
&+P(p=p_{1})P(\text{type 2 error})K_{0} \\
&= \frac{2}{3}0.18K_{0}+\frac{1}{3}0.51K_{0}
\end{align}
$$
**f)**
Make it an equalizer rule:
$$
\begin{align}
R(\delta,p_{0}) &= R(\delta,p_{1}) \\
\frac{2}{3}0.09cK_{0} &= \frac{1}{3}0.51K_{0} \\
c &= \frac{1}{2}\frac{0.51}{0.09} \\
c &= 2.889
\end{align}
$$
