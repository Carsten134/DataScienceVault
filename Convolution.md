Let $W,\tilde{W}$ be [[Linear filter]]s. Then we notate the successive application (**convolution**) of these filters as:
$$
V =W\tilde{W} = W \circ \tilde{W}
$$
Then the weights $v_{k}$ can be derived as:
$$
v_{k} = \sum_{j}\tilde{w}w_{k-j}
$$
And the individual weights can be notated as:
$$
v_{k} = (w_{i})*(\tilde{w}_{j})
$$
## Properties of convolution
- Associative
- Commutative

## Translation to [[z-transform]]:
The z-transform of a convolution of two linear filters is exactly the product of their individual z-transforms:
$$
f_{W\circ V}(z)= f_{W}(z)f_{V}(z)\hspace{1em} \forall z\in \mathbb{C}
$$

