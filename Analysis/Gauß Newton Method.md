- Let’s say you want to estimate a parametric function $m(t,\theta)$ but $\theta$ is not a linear parameter (so an analytic solution to least squares becomes difficult to find out and also requires a lot of compute)
- We want to apply a holistic approach to estimation.
- Solution Gauß-Newton method:
	1. approximate $m(t,\theta)$ using [[Taylor Approximation]] first order:
	$$ m(t,\theta) \approx m(t,\theta_0)+(\theta-\theta_0)m'(t,\theta_0) =m(t,\theta_0)+\Delta m'(t,\theta_0) $$
	
	1. Then apply [[OLS]] to estimate $\Delta$ to get $\hat \Delta$.
	2. Then choose $\theta_1 = \theta_0 +\Delta$
	3. Repeat 1-3 till $\theta_p$ behaves convergent