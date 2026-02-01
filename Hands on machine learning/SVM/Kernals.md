## the Kernel Trick 🚀

### Key SVM fact (this is crucial)

The SVM optimization **never needs ϕ(x)\phi(x)ϕ(x) directly**.

It only needs:

$ϕ(xi)Tϕ(xj)\phi(x_i)^T \phi(x_j)ϕ(xi​)Tϕ(xj​)$

So we define a **kernel function**:

$K(xi,xj)=ϕ(xi)Tϕ(xj)K(x_i, x_j) = \phi(x_i)^T \phi(x_j)K(xi​,xj​)=ϕ(xi​)Tϕ(xj​)$

👉 We compute the inner product **without ever computing ϕ\phiϕ**.

That’s the kernel trick.
#### There are different kernals 
- Linear Kernel- $K(xi​,xj​)=xi^T​xj​$
- Polynomial Kernel - $K(xi​,xj​)=(xi^T​xj​+c)d$
- RBF (Gaussian) Kernel — the GOAT - $K(xi​,xj​)= e^{(−γ∥xi​−xj​∥2)}$ 
- Sigmoid Kernel - $K(xi​,xj​)=tanh(αxiT​xj​+c)$ 