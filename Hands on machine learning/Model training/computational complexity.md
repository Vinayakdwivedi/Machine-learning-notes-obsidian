| **Feature**     | **Normal Equation**                                        | **SVD (Pseudoinverse)**                                  |
| --------------- | ---------------------------------------------------------- | -------------------------------------------------------- |
| **Formula**     | $$(\mathbf{X}^T \mathbf{X})^{-1} \mathbf{X}^T \mathbf{y}$$ | $$\mathbf{V} \mathbf{\Sigma}^+ \mathbf{U}^T \mathbf{y}$$ |
| **Complexity**  | $O(m n^2 + n^3)$                                           | $O(m n^2)$ (higher constants)                            |
| **Speed**       | Faster for small $n$                                       | Slower                                                   |
| **Stability**   | Unstable if $\mathbf{X}^T \mathbf{X}$ is singular          | **Extremely Stable**                                     |
| **Requirement** | Needs $\mathbf{X}^T \mathbf{X}$ to be invertible           | Works on any matrix                                      |
