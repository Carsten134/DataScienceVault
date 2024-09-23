Here are some default strategies for showing convergence:
# In distribution
1. Try Levy's continuity theorem
2. Otherwise you can try to show $F_{X_{n}}(x) \to F_{X}(x)$ **for all continuity points**
3. iid? with common and finite mean and variance?
	1. Use Lindeberg-Levy CLT
		- Especially when the term looks something like: $\sqrt{ n }(X_{n}-\mu)$
	2. If this does not fit, you can try to combine it with either delta-method or continuous mapping theorem
4. To constant?
	1. In that case showing convergence in probability (or even $L_{1}$) works better.
5. Multivariate?
	1. Try Cramer-Wold device together with Levy's continuity theorem.
6. Complicated sequence?
	1. Try Slutsky's-Lemma (to decompose the sequence) together with LLN (for the constant part).
# Convergence in probability
1. To a constant? ($X_{n}\overset p \longrightarrow a$)
	1. $X_{n} = \bar{X}_{n}$ sample mean? use LLN 
		1. Some transformation of the mean ($X_{n} = g(\bar{X}_{n})$)? Use LLN together with continuous mapping theorem. 
	2. Common mean and decreasing variance? Use Chebyshev-ineq.
	3. No common mean? Center and try Markov
		- Take specific care of the absolute values:
		- $P(|X_{n}|> \epsilon) \neq P(X_{n}>\epsilon)$
	4. No decreasing variance? Try to show $L_{1}$ convergence
2. Other things to consider:
	1. What side of convergence are you showing? $P(|X_{n}-X|> \epsilon)$ or $P(|X_{n}-X|\leq \epsilon)$?

# Almost sure
1. iid + common mean + $X_{n} = \bar{X}_{n}$? -> Try strong LLN
	- Also don't forget, that you can combine it with continuous mapping theorem
2. When proving manually:
	- Remember you are trying to show, that:
		- $P(\omega\in \Omega: X_{n} \to X) = 1$
		- So in total you concentrate on the $\omega \in \Omega$ for which $X_{n}(\omega)$ converges point-wise to $X(\omega)$
	- always look at the probability measure first:
		- Lebesgue measure -> You can discard singleton sets (even up to countable infinite unions like the rational numbers $\mathbb Q$)
		- Dirac measure $\delta_{\omega}$-> Ignore everything except $\omega$.

# $L_{p}$ convergence
1. Often $L_{p}$ convergence is just handling expected values correctly and using analysis to find the limit-point.
2. Remember:
	1. $\varphi_{X_{n}}^{(k)}(0) = i^k \mathbb{E}(X^k)$
	2. $M_{X_{n}}^{(k)}(0) = \mathbb{E}(X^k)$ where $M_{X}$ is the moment generating function
	3. L' Hospital: $\lim_{ n \to \infty } \frac{a_{n}}{b_{n}} = \lim_{ n \to \infty } \frac{a'_{n}}{b'_{n}}$

## Use implications 
![[Pasted image 20240916142905.png]]
- Sometimes it is easier to show $L_{1}$ convergence instead of probability
- Or show a.s. convergence instead of distribution or probability
- Really memorize these logic structures

### When can you go back?
$$
X_{n} \overset p \longrightarrow a \Longleftrightarrow X_{n} \overset d \longrightarrow a \hspace{1em} \forall a\in\mathbb{R}
$$
Convergence to a constant in probability or distribution enables you to show distribution and imply probability.

# Useful expressions to know:
$$
\begin{align}
\exp(x) &= \lim_{ n \to \infty }\left( 1+ \frac{x}{n} \right)^n = \sum_{k=1}^\infty \frac{x^k}{k!}  \\
\sum_{k=0}^\infty a\cdot x^k &= \frac{a}{1-x} \hspace{1em} \forall |x|<1 \text{ Geometric series}\\
\sum_{k=0}^\infty \frac{1}{k} &= \infty \hspace{1em} \text{Harmonic series}\\
\lim_{ n \to \infty } \frac{n+1}{n} &= 1 \\
|\exp(it)| &=1  
\end{align}
$$