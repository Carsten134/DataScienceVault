#timeseriesanlysis 
Is a model, where a [[Time Series]] $y_{t}$ can be decomposed into **multiplicative** components:
$$
y_{t} =m_{t}z_{t}u_{t}
$$
- $m_{t}$ is the **trend**
- $z_{t}$ is the **cyclical** component
- $u_{t}$ are the **shocks**
By log-scaling the model we get:
$$
y_{t} = \log m_{t}+\log z_{t}+\log u_{t}
$$
which is the [[Additive Components Model]] with log scaled components