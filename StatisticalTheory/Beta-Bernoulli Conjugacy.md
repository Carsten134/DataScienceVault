#bayesianstats
Given the setup $y_{i}|\theta\sim Ber(\theta)$ and $\theta\sim \Gamma(\alpha, \beta)$:
$$
p(\theta|y)\propto p(y|\theta)p(\theta)
$$
And this gives us the estimation problem for maximizing the posterior:
$$
\max_{\theta \in \mathbb{R}} \theta^{\sum_{i=1}^ny_{i}-1+\alpha}(1-\theta)^{\beta-1+n-\sum_{i=1}^ny_{i}}
$$
But this is equivalent to:
$$
\max_{\theta\in \mathbb{R}}\ln(\theta)\left( \sum_{i=1}^ny_{i}-1+\alpha \right) +\left( \beta-1+n-\sum_{i=1}^ny_{i} \right) \ln(1-\theta)
$$
FOC yields:
$$
\frac{\left( \sum_{i=1}^ny_{i} -1+\alpha\right)}{\theta}-\frac{\left( \beta-1+n-\sum_{i=1}^ny_{i} \right)}{1-\theta} = 0
$$
And that is equivalent to:
$$
\theta \left( -\left( \sum_{i=1}^ny_{i} -1+\alpha\right) -\left( \beta-1+n-\sum_{i=1}^ny_{i} \right)\right) +\left( \sum_{i=1}^ny_{i} -1+\alpha\right)=0
$$
We see now that the sum is cancelled out and all that is left is:
$$
\theta \left( 2-\alpha-\beta-n \right) =-\sum_{i=1}^ny_{i} +1-\alpha
$$
Divide by $(2-\alpha-\beta-n)$ and get:
$$
\hat{\theta} = \frac{\left( -\sum_{i=1}^ny_{i}+1-\alpha \right)}{2-\alpha-\beta-n} = \frac{\left( \sum_{i=1}^ny_{i}-1+\alpha \right)}{n+\alpha+\beta-2}  
$$
