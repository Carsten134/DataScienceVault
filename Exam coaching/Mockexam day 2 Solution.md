# Problem 1.1
**a)**
The Borel-$\sigma$-Algebra is the smallest $\sigma$-Algebra containing all intervals:
$$
\mathcal B(\mathbb{R}) = \sigma(\{[a,b] \subset \mathbb{R} \}\})
$$
**b)**
Let $(A_{n})_{n\in \mathbb N}\in \mathcal A$  (so a sequence in the $\sigma$-Algebra). Then it holds that:
$$
\begin{align} \\
\implies (A_{n}^c)_{n\in\mathbb N} \in\mathcal A \\

\implies \bigcup_{i=1}^\infty A_{i}^c \in \mathcal A \\
\overset{\text{de morgan}}\Longleftrightarrow  \left( \bigcap_{i=1}^\infty A_{i} \right)^ c \in \mathcal A \\
\implies \bigcap_{i=1}^n A_{i} \in \mathcal A 
\end{align}
$$
**c)**
Let $x\in\mathbb{R}$, then we define: 
$$
A_{n} := \left[ x,x+\frac{1}{n} \right]
$$
And since $\frac{1}{n}\to {0}$ as $n\to \infty$  and $A_{n+1} \subset A_{n} \forall n$ it holds that:
$$
\bigcap_{i=1}^\infty A_{i} = \lim_{ n \to \infty } A_{n} = [x,x+0] = \{x\}
$$
And (using the result from b)):
$$
\{x\}=\bigcap_{i=1}^\infty A_{i}\in \mathcal B(\mathbb{R})
$$
**d)**
A classic is Borel, Lebesgue combination:
$$
([0,1], \mathcal B([0,1]),\lambda)
$$

# Problem 1.2
**a)**
$$
\begin{align}
P(A) &\geq 0 \hspace{1em} \forall A\in\mathcal A \\
P(\Omega) &= 1 \\
P \left( \biguplus_{i=1}^\infty A_{i}\right) &=\sum_{i=1}^\infty P(A_{i}) \hspace{1em} \forall (A_{n})_{n\in\mathbb N}\in \mathcal A
\end{align}
$$
**b)**
Using lemma 1.2 from the lecture:
$$
P(A) = \sum_{a\in A} P(\{a\})
$$
So:
$$
P(A) = \sum_{a\in A} P(\{a\}) \geq \sum_{a\in A}0 =0
$$
And:
$$
\begin{align}
P(\mathbb{N}) &= \sum_{n\in \mathbb N  \setminus \{0\}} \frac{1}{2^n} \\
&= \sum_{n=0}^\infty \frac{1}{2 ^n}-1 \\
&= \frac{1}{1-\frac{1}{2}}  -1 = 2-1 = 1
\end{align}
$$
Finally showing sigma-additivity:
$$
\begin{align}
P\left( \biguplus_{i=1}^\infty A_{i} \right) &= \sum_{a\in \biguplus_{i=1}^n A_{i}}P(\{a\}) \\
&= \sum_{i=1}^\infty \sum_{a\in A_{i}} P(\{a\}) \\
&= \sum_{i=1}^\infty P(A_{i})  
\end{align}
$$
**c)**
The event is assigned the probability:
$$
\begin{align}
P(\{C, \dots, K\}) &= \sum_{i=C}^K \frac{1}{2^i} \\
&= \left( \frac{1}{2  ^C}+ \cdots+\frac{1}{2^K} \right) 
\end{align}
$$
**d)**
For this r.v. it holds that $X(\omega) = 1$ for even $\omega$  (excluding 0) and $X(\omega) = 0$ for odd $\omega$. So we can express the expected value as:
$$
\begin{align}
\mathbb{E}(X) &= 1\cdot P(X=1) + 0 \cdot P(X=0) \\
&= P(X=1) \\
&=\sum_{k=1}^\infty \frac{1}{2^{2k}} \\
&= \sum_{k=0}^\infty \frac{1}{2^{2k}}-1 \\
&= \frac{1}{1-\frac{1}{4}}-1  \\
&= \frac{4}{3}-1 = \frac{1}{3} 
\end{align}
$$
# Problem 1.3
**a)**

Let $\epsilon>0$ and $x\in \mathbb{R}$. In the case that $x\leq 0$ it holds that:
$$
X_{n}(x) = 0 \hspace{1em} \forall n\in\mathbb N
$$
But that means that:
$$
X_{n}(x) \to 0 \hspace{1em}\forall x\leq 0
$$
For $x > 0$ it holds that:
$$
\exists n_{x} \in\mathbb N: x> \frac{1}{2n} \hspace{1em} \forall n>n_{x}
$$
Therefore:
$$
\exists n_{x}\in\mathbb N: X_{n}(x) =0 \hspace{1em} \forall n>n_{x}
$$
and:
$$
|X_{n}(x)-0| <  \epsilon \hspace{1em} \forall n>n_{x}
$$
Which is equivalent to:
$$
X_{n}(x) \to 0 \hspace{1em} \forall x>0
$$
So in total we can say:
$$
X_{n}(x) \to 0 \hspace{1em} \forall x\in \mathbb{R}
$$
Looking at the expected value asymptotically:
$$
\begin{align}
\mathbb{E}\left( \lim_{ n \to \infty }X_{n} \right)  &= \mathbb{E}(0) = 0
\end{align}
$$
And:
$$
\begin{align}
\lim_{ n \to \infty } \mathbb{E}(X_{n}) &= \lim_{ n \to \infty } \int_{0}^1 X_{n}d \lambda \\
&= \lim_{ n \to \infty } 2n \lambda(X^{-1}(\{2n\}))+ 0\cdot \lambda(X^{-1}(\{0\})) \\
&= \lim_{ n \to \infty } 2n \lambda\left(\left( 0, \frac{1}{2n}\right] \right) \\
&= \lim_{ n \to \infty } \frac{2n}{2n} = 1
\end{align}
$$
So it holds that:
$$
\mathbb{E}\left( \lim_{ n \to \infty } X_{n}  \right) \neq \lim_{ n \to \infty }  \mathbb{E}(X_{n})
$$
**b)**
Intuitively it does not hold, because there is no convergence in expectation. But note, that monotone sequences imply convergence in expectation but convergence in expectation does not imply monotone sequences.

# Problem 2.1
**a)**
$$
\begin{align}
\mathscr X &= \mathbb{R}^n \\
\Theta &= \mathbb{R} \\
D &= \begin{cases}
\delta_{0} \\
\delta_{1}  
\end{cases}= \begin{cases}
\text{accept H}_{0} \\
\text{reject H}_{0}
\end{cases} \\
L &= \text{0-1 loss}
\end{align}
$$
**b)**
Any linear combination of normal random variables is also normal. We therefore only need to find the expectation and variance.
$$
\begin{align}
\mathbb{E}(T(\vec{X}))&= \frac{1}{\sqrt{ n }\sigma}\sum_{i=1}^n \mathbb{E}(X_{i}) \\
&= \frac{1}{\sqrt{ n }\sigma} \sum_{i=1}^n 0 \hspace{1em} \text{H}_{0} \\
&= 0 \\
Var(T(\vec{X})) &= \frac{1}{n\sigma ^2} \sum_{i=1}^n Var(X_{i}) \\
&= \frac{1}{n \sigma}n \sigma ^2 = 1
\end{align}
$$
So in total:
$$
T(\vec{X}) \sim \mathcal N(0,1) \hspace{1em} \text{under }H_{0}
$$
**c)**
$$
\begin{align}
\alpha &= P_{\mu=0}(|T(\vec{X})|\geq 1.645) \\
&= 1-P(|T(\vec{X})|<1.645) \\
&= 1-P(-1.645 < T(\vec{X})< 1.645) \\
&= 1-\Phi(1.645) + \Phi(-1.645)  \\
&= 1-95\% +5 \% = 10\%
\end{align}
$$
**d)**
Walds test, it tests the difference between the restricted estimate and unrestricted estimate. 

In total this test is known as the standard T-test and is probably the first thing every statistics student gets introduced to, when they first start out.

**e)**
$$
R( \phi(\vec{X}), \mu) = \begin{cases}
P(|T(\vec{X})|\geq 1.645) & \mu  = 0 \\
P(|T(\vec{X})|<1.645) & \mu \neq 0
\end{cases}
$$
# Problem 2.2
**a)**
$$
\begin{align}
\mathscr X &= \mathbb N^n \\
\Theta &= (0,\infty) \\
D &= \Theta \\
L &= (\delta-\lambda)^ 2
\end{align}
$$
**b)**
Using Bayes rule:
$$
\begin{align}
f(\lambda|\vec{X}) &\propto \mathcal L(\vec{X}|\lambda) g(\lambda) \\
&= g(\lambda)\prod_{i=1}^n f(x_{i}|\lambda)  \\

&= \frac{\beta^\alpha}{\Gamma(\alpha)}\lambda^{\alpha-1}\exp(-\beta \lambda) \prod_{i=1}^n \frac{\lambda^{x_{i}}}{x_{i}!}\exp(-\lambda) \\
&\propto \lambda^{\alpha-1}\exp(-\beta \lambda) \lambda^{\sum_{i=1}^n x_{i}}\exp(- n\lambda) \prod_{i=1}^n \frac{1}{x_{i}!} \\
&\propto \lambda^{\alpha + \sum_{i=1}^n x_{i}-1}\exp(-(\beta+n)\lambda)
\end{align}
$$
This is a kernel of the density of the gamma distribution. So we can therefore say:
$$
\lambda |\vec{X}  \sim \text{Gamma}\left( \alpha +\sum_{i=1}^n x_{i}, n+ \beta \right)
$$
**c)**
The Bayes rule for the squared loss is always the conditional expectation:
$$
\delta_{B}(\vec{X}) = \mathbb{E}(\lambda|\vec{X}) = \frac{ \alpha + \sum_{i=1}^n x_{i}}{n+ \beta}
$$
