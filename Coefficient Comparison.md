Is a way of finding the inverse of a [[Linear filter]]. So let $W$ be a linear filter and $V$ it's inverse (we assume that the inverse exists). We know that the inverse is unique and has the property:
$$
W\circ V = 1
$$
Inserting the definition of a linear filter this means that:
$$
\begin{align}
\left( \sum_{j\in \mathbb{Z}}w_{j}B^j \right)\left( \sum_{j\in \mathbb{Z}} v_{j}B^j\right)   &=1 \\
\end{align}

$$
This directly translates to two conditions:
$$
\begin{align}
\sum_{j\in \mathbb{Z}}v_{j}w_{-j} &= 1 \\
\sum_{j\in \mathbb{Z}}v_{j}w_{k-j} &= 0 \hspace{1em} \forall k \neq 0
\end{align}
$$
Using these two conditions you can derive any inverse for any finite linear filter, by extracting the equations.