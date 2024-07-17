#montecarlo 
This is for the R-Code provided to us by the lecturer.
The model (or at least that is what i assume):
$$
y_{i} = \beta_{0}+\beta_{1}x_{i}+ \varepsilon_{i}
$$

And the mean for $\beta_{1}$:
$$
\bar{\beta_{1}} = \frac{\sum_{i=1}^n(x_{i}-\bar{x})(y-\beta_{0})}{\sum_{i=1}^n(x_{i}-\bar{x})^2}
$$
And $\bar{\beta_{0}}$:
$$
\bar{\beta_{0}} = \bar{y}-\beta_{1}\bar{x}
$$
So this is just the OLS estimate for a normal linear regression. Nothing special. But 