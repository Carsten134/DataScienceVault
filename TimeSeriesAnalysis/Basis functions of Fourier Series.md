#linearalgebra #frequencyanalysis #timeseriesanlysis 
This Note is on the basis functions of the [[Fourier Series]]. 
We know that if we have a [[Time Series]] of length $T, y_t$ we can interpret this as a vector $y\in\mathbb R^T$. And it holds that 
$$y_t = \sum_{k=1}^{\frac T2}a_k \sin\left(2\pi\frac{t}{T}k\right)+ b_k\cos\left(2\pi\frac tT k\right)$$
This can also be rewritten in vector form and then becomes the linear combination of these vectors:
$$
y = \begin{pmatrix}y_1 \\
\vdots \\
y_{T}\end{pmatrix} =\sum_{k=1}^{\frac{T}{2}}a_{k}\begin{pmatrix}
\sin \left( \frac{2\pi 1}{T}k  \\\right) \\
\sin \left( \frac{2}{T}2\pi k \right)   \\
\vdots \\
\sin \left( \frac{T}{T}2\pi k \right)
\end{pmatrix}
+ b_{k} \begin{pmatrix}
\cos \left( \frac{1}{T}2\pi k \right) \\
\cos \left( \frac{2}{T} 2\pi k \right)  \\
\vdots \\
\cos \left( \frac{T}{T}2\pi k \right) 
\end{pmatrix}
$$
So the vector created by $\sin\left( \frac{t}{T} 2\pi k \right)$ with $t \in \{1,..,T\}$ is a basis vector that spans the [[Vector space]] in which $y$ lives.
In short:
$$
\mathcal B =\left\{\begin{pmatrix}
\cos \left( \frac{1}{T}2\pi 1 \right) \\
\cos \left( \frac{2}{T} 2\pi 1 \right)  \\
\vdots \\
\cos \left( \frac{T}{T}2\pi 1 \right) 
\end{pmatrix},\cdots, \begin{pmatrix}
\cos \left( \frac{1}{T}2\pi \frac T 2  \right) \\
\cos \left( \frac{2}{T} 2\pi \frac T 2  \right)  \\
\vdots \\
\cos \left( \frac{T}{T}2\pi \frac T 2 \right) 
\end{pmatrix}, \begin{pmatrix}
\sin  \left( \frac{1}{T}2\pi \frac T 2  \right) \\
\sin \left( \frac{2}{T} 2\pi \frac T 2  \right)  \\
\vdots \\
\sin \left( \frac{T}{T}2\pi \frac T 2 \right) 
\end{pmatrix}\right\}
$$
Is a [[Basis]] for $\mathbb{R}^T$ In other notation with [[Base angular frequency]]:
$$
\mathcal B =\left\{\begin{pmatrix}
\cos \left( \omega_{1}1 \right) \\
\cos \left( \omega_{1}2 \right)  \\
\vdots \\
\cos \left( \omega_{\frac{T}{2}}T\right) 
\end{pmatrix},\cdots, \begin{pmatrix}
\cos \left( \omega_{\frac{T}{2}}1 \right) \\
\cos \left( \omega_{\frac{T}{2}}2 \right)  \\
\vdots \\
\cos \left( \omega_{2}T \right) 
\end{pmatrix}, \begin{pmatrix}
\sin  \left( \omega_{\frac{T}{2}}1 \right) \\
\sin \left( \omega_{\frac{T}{2}}2\right)  \\
\vdots \\
\sin \left( \omega_{\frac{T}{2}}T\right) 
\end{pmatrix}\right\}
$$
