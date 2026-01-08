
$$
\begin{aligned}
\text{1. Define the Cost Function (SSR):} \\
V(\beta) &= (\mathbf{y} - \mathbf{X}\beta)^T (\mathbf{y} - \mathbf{X}\beta) \\
\\
\text{2. Expand the terms:} \\
V(\beta) &= \mathbf{y}^T \mathbf{y} - \mathbf{y}^T \mathbf{X}\beta - \beta^T \mathbf{X}^T \mathbf{y} + \beta^T \mathbf{X}^T \mathbf{X}\beta \\
\\
\text{3. Simplify (since } \mathbf{y}^T \mathbf{X}\beta \text{ is a scalar):} \\
V(\beta) &= \mathbf{y}^T \mathbf{y} - 2\beta^T \mathbf{X}^T \mathbf{y} + \beta^T \mathbf{X}^T \mathbf{X}\beta \\
\\
\text{4. Take the derivative with respect to } \beta: \\
\frac{\partial V}{\partial \beta} &= -2\mathbf{X}^T \mathbf{y} + 2\mathbf{X}^T \mathbf{X}\beta \\
\\
\text{5. Set to zero to find the minimum } (\hat{\beta}): \\
0 &= -2\mathbf{X}^T \mathbf{y} + 2\mathbf{X}^T \mathbf{X}\hat{\beta} \\
2\mathbf{X}^T \mathbf{X}\hat{\beta} &= 2\mathbf{X}^T \mathbf{y} \\
\mathbf{X}^T \mathbf{X}\hat{\beta} &= \mathbf{X}^T \mathbf{y} \\
\\
\text{6. Solve for } \hat{\beta}: \\
\hat{\beta} &= (\mathbf{X}^T \mathbf{X})^{-1} \mathbf{X}^T \mathbf{y}
\end{aligned}
$$
