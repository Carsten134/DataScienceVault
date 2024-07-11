#timeseriesanlysis 
We later learn, because of the [[Wold decomposition]], that the existence of an inverse is very important, when thinking about [[Linear filter]]s. Therefore we need some conditions, that prove the existence.

# for finite linear filters
For finite linear filters we get the existence of an inverse iff the [[Characteristic Polynomial]] has no roots with absolute value 1:
$$
\nexists z\in \mathbb{C}| \lvert z \rvert = 1: p(z)=0
$$
## Translation to [[z-transform]]:
This expression:
$$
W\circ W^{-1} = 1
$$
Is exactly equivalent to:
$$
f_{W\circ W^{-1}}(z)=f_{W}(z)f_{W^{-1}}(z) = 1
$$
But this means that:
$$
f_{W^{-1}}(z) = \frac{1}{f_{W}(z)}
$$
We also know, that $W^{-1}$ is a linear filter. So we can also apply the z-transform on that:
$$
f_{W^{-1}}(z) = \sum_{j\in \mathbb{Z}}\tilde{w}_{j}z^j
$$
But we also know, that the [[Laurent Series expansion]] is convergent around an [[annulus]] around 1 (due to absolute summability). Naturally the it follows, that $f_{W^{-1}}(z)$ MUST behave convergent for all $z$ with $\lvert z \rvert= 1$. But this means that:
$$
f_{W}(z) \neq 0 \hspace{1em}\forall z: \lvert z \rvert=1  
$$
### Translation to [[Causal linear filter]]s
In this case, we can treat the z-transform $f_{W}(z)$ as a [[geometric series]]. Therefore the annulus becomes just the unit circle. Now we need:
$$
f_{W}(z) \neq 0 \hspace{1em} \forall \lvert  z \rvert \leq 1
$$