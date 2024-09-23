# Problem 1.1
a)
Let $X:\Omega_{1} \to \Omega_{2}$ be a mapping with $\mathcal A_{1}$ and $\mathcal A_{2}$ being $\sigma$-Algebras for the respective sets $\Omega_{1}, \Omega_{2}$. Then $X$ is $(\mathcal A_{1}-\mathcal A_{2})$measurable iff:
$$
X^{-1}(A) \in \mathcal A_{1} \forall A\in\mathcal A_{2}
$$
b) 
Holds by definition of the powerset:
$$
Z^{-1}(A)\in \mathcal P(\Omega) \hspace{1em} \forall A\in\mathcal P(\Omega')
$$
For the preimages:
$$
\begin{align}
Z^{-1}(\{0\}) &= \{(1,1), (2,2),(3,3), (4,4)\} \\
Z^{-1}(\{1\}) &= \{(1,2), (2,1), (2,3), (3,2), (3,4), (4,3)\} \\
Z^{-1}(\{2\}) &= \{(1,3), (3,1), (2,4), (4,2)\} \\
Z^{-1}(\{3\}) &= \{(1,4), (4,1)\}
\end{align}
$$
c)
The expected value:
$$
\begin{align}
\mathbb{E}(Z) &= \sum_{i=0}^3 \omega P(Z^{-1}(\omega)) \\
&= 0\cdot P(\{(0,0),\dots,(4,4)\}) + 1\cdot 0+2 \cdot 0+ 3 \cdot 0 \\
&= 0\cdot \sum_{i=0}^3 \frac{1}{4} + 1\cdot 0+2 \cdot 0+ 3 \cdot 0\\
&= 0\cdot 1 = 0
\end{align}
$$
Variance:
$$
\begin{align}
Var(Z) &= \mathbb{E}(Z^2)-\mathbb{E}(Z)^2 \\
&= \sum_{\omega =1}^3 \omega^2P(Z^{-1}(\{\omega\}))-0^2 \\
&= 0^2 \cdot P(\{\dots\})+1 \cdot 0+2\cdot 0+3\cdot 0 \\
&= 0-0 = 0
\end{align}
$$
d)
$$
\begin{align}
\mathbb{E}(Z_{1}) &= \sum_{\omega=0}^3\omega P(Z^{-1}_{1}(\{\omega\})) \\
&= \sum_{\omega=0}^3 \omega P(\{(\omega,\omega)\}) \\
&= \sum_{\omega=0}^3 \omega \frac{1}{4} \\
&= \frac{1}{4}\cdot 6 = 1.5
\end{align}
$$
And the variance:
$$
\begin{align}
Var(Z_{1})&= \mathbb{E}(Z_{1}^2) -\mathbb{E}(Z_{1})^2 \\
&= \sum_{\omega =0}^3 \omega^2 P((\{\omega,\omega\}))-1.5^2 \\
&= \sum_{\omega=0}^3 \omega^2 \frac{1}{4} - 1.5^2 \\
&= \frac{1}{4} 14 - 2.25 \\
&= 3.5-2.25 = 1.25
\end{align}
$$
# Problem 1.2 
a)  We need to show
$$
\begin{align}
f_{X_{1}}(x) \geq 0 \hspace{1em } \forall x\in \mathbb{R} \\
\int_{\mathbb{R}}f_{X_{1}}(x) dx= 1
\end{align}
$$
For 1):
$$
f_{X_{1}}(x) = 3x^2\cdot 1_{[0,1]}(x) \geq 0
$$
And 2)
$$
\begin{align}
\int_{\mathbb{R}}f_{X_{1}}(x)dx &= 3 \int_{0}^1 x^2 dx \\
&= 3 \left[ \frac{1}{3}x^3 \right]_{0}^1 \\
&= \frac{3}{3} = 1
\end{align}
$$
So the expected value is:
$$
\begin{align}
\mathbb{E}(X_{1}) &= \int_{\mathbb{R}}xf_{X_{1}}(x)dx \\
&= \int_{\mathbb{R}}x 3 x^2 \cdot 1_{[0,1]}(x)dx \\
&= 3\int_{0}^1x^3dx  \\
&= 3 \left[ \frac{1}{4}x^4 \right]_{0}^1 \\
&= \frac{3}{4} 
\end{align}
$$
b)
$$
\begin{align}
\mathbb{E}(X_{2}) &= \int_{[0,1]}X_{2}d\lambda \\
&= \sum_{i \in \left\{ \frac{1}{4}+C, 3+C, \frac{2}{3}+C \right\}} i \lambda(X_{2}^{-1}(\{i\})) \\
&= \left(  \frac{1}{4}\lambda([0,0.5)) +3 \lambda([0.5,0.7)) + \frac{2}{3}\lambda([0.7,1))\right) +C \\
&= \frac{1}{4} \frac{1}{2} + \frac{3}{5}+\frac{2}{3} \frac{3}{10} +C\\
&= \frac{1}{8}+ \frac{3}{5}+ \frac{3}{15} +C
\end{align}
$$
c)
This is the density of a normal so:
$$
X_{3} \sim \mathcal N(0, \sigma^2)
$$
And this implies that:
$$
\mathbb{E}(X_{3}) = 0 
$$
d)
$$
\begin{align}
\mathbb{E}(X_{4}) &=  \lambda(\mathbb Q \cap [0,1]) \\
&= \sum_{x\in \mathbb Q\cap [0,1]}\lambda(\{x\}) \\
&=  \sum_{x\in\mathbb Q\cap[0,1]} 0 \\
&= 0 
\end{align}
$$
e) 
Now for $X_{2}$ we get:
$$
\begin{align}
\mathbb{E}(X_{2}) &= C \cdot \delta_{1}(X_{2}^{-1}(\{C\})) + \left( C+\frac{1}{4} \right)\delta_{1}([0,0.5))+\dots\\
&= C \cdot \delta_{1}(\{1\}) + \left( C+\frac{1}{4} \right)\cdot  0 \\
&= C \cdot 1  = 1 \\
\end{align}
$$
And $X_{4}$:
$$
\begin{align}
\mathbb{E}(X_{4}) &= 1\cdot \delta_{1}(\mathbb Q\cap [0,1]) \\
&= 1 \cdot 1
\end{align}
$$
# Problem 1.3
a) 
Two sets from a $\sigma$-Algebra are stochastically independent iff:
$$
P(A\cap B) = P(A)P(B)
$$
b)
We choose the sets:
$$
\begin{align}
A_{1} &= [0,0.5]\times [0,1] \\
A_{2} &= [0.25, 0.75] \times [0,1]
\end{align}
$$
Then it holds that:
$$
\lambda(A_{1}\cap A_{2}) = \frac{1}{4}
$$
And:
$$
\begin{align}
\lambda(A_{1}) = \frac{1}{2}\cdot 1 \\
\lambda(A_{2}) = \frac{1}{2}\cdot 1 \\
\implies \lambda(A_{1})\lambda(A_{2}) &= \frac{1}{2^2} = \frac{1}{4}
\end{align}
$$
c)
$$
\begin{align}
Z^{-1}(\{3\}) &= [0,0.5]\times [0,1] \\
Z^{-1}(\{2\}) &= (0.5, 1] \times [0,1] \\
\mathbb{E}(Z)& = \sum_{i\in \{2,3\}} i\lambda(Z^{-1}(\{i\})) \\
&= 2 \cdot \frac{1}{2}+\frac{3}{2} = 2.5
\end{align}
$$
# Problem 2.1
e)
With a)
$$
R(\delta_{M}, \theta_{1}) = R(\delta_{M},\theta_{2}) = 1
$$
with b) we'll say $x = R(\delta_{M}, \theta_{1}) -1 = R(\delta_{M},\theta_{2})-1$
$$
\begin{align}
2x ^2 &= 1 \\
x^2 &= \frac{1}{2} \\
x &= \pm \frac{1}{\sqrt{ 2 }}
\end{align}
$$
with c)
$$
R(\delta_{M},\theta_{1}) = R(\delta_{M},\theta_{2}) = \frac{1}{2}
$$
with d)
$$
\begin{align}
x &\geq x^{-1} \\
x^2 &\geq 1 \\
x &= \pm 1
\end{align}
$$
# Problem 2.2
For $\delta_{0}$ we have:
$$
\begin{align}
L(\delta_{0}, \theta) &= \min\left\{ \left| \frac{\theta}{\theta} \right|  , 3\right\}  \\
&= \min \{1,3\} = 1
\end{align}
$$
For any other rule we can find $\vec{x}\in \mathscr X$ such that:
$$
\delta(\vec{x}) = c >0
$$
and therefore if we let $\theta \to 0$:
$$
\begin{align}
L(\delta,\theta) &= \min\left\{ \left| \frac{c}{\theta}-1 \right|,3  \right\}  \\
&= 3 > L(\delta_{0},\theta)
\end{align}
$$
Because as $\theta\to 0$ it holds that $\frac{c}{\theta}\to \infty$  and therefore $\left| \frac{c}{\theta}-1 \right|\to \infty$
Therefore any rule is R-incomparable to $\delta_{0}$. $\delta_{0}$ is thus admissible and together with it's equalizer property we have shown, that $\delta_{0}$ is minimax.