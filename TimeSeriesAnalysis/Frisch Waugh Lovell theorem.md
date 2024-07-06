#timeseriesanlysis 
We are in the [[Additive Components Model]] and assume linear trend $m_{t}$ and seasonal components $s_{t}$ and a shocks $u_{t}$:
$$
y_{t } = \beta_{0}+\beta_{1}t+ \delta_{1}(s_{1,t}-s_{4,t})+\dots+u_{t}
$$
Expressing this as matrix form:
$$
y = Z\beta+S\delta+u
$$
and solving with [[OLS]], this theorem shows, that there always exists a solution to this optimization problem.