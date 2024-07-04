#estimation
#montecarlo
Given a sample $\{x_{1},\dots,x_{n}\}$ we can resample (with replacement) from this sample to create new samples. Then we can do repeated inference on the generated to samples, to reduce the variance of our estimate.

## Downfalls
Do not use if:
- Data is biased
- u have small sample sizes
- 