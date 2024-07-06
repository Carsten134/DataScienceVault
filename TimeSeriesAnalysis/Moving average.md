#timeseriesanlysis 
Let $Y_{t}$ be a [[Time Series]] and $W$ a [[Linear filter]], that has only equal weights and is symmetrical:
$$
W(B) = \sum_{i=-k}^k \frac{ 1 }{2k+1} B^i
$$
Then:
$$
\hat{m_{t}} = W(B)Y_{t}
$$
Is a **moving average** and is a [[smoothing method]] to extract low frequency components or trends from the  [[Time Series]] $Y_{t}$.

## what if we want $2k$ observations?
We can use right and left averages:
$$
\begin{align}
\hat{m}_{t}^L &= \frac{1}{4}(y_{t-2}+y_{t-1}+y_{t}+y_{t+1}) \\
\hat{m}_{t}^R &= \frac{1}{4}(y_{t-1}+y_{t}+y_{t+1}+y_{t+2})
\end{align}
$$
Then average them out.
## Padding of the time-series
We can extend the time-series by putting $k$ times $y_{1}$ at the beginning and $y_{T}$ at the end. Such that we get:
$$
\hat{m}_{1},\dots,\hat{m}_{T}
$$
estimates instead of $T-2k$
