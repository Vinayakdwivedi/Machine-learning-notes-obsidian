### 1. The Core Concept

SVD states that any $m \times n$ matrix $\mathbf{A}$ can be factored into:

$$\mathbf{A} = \mathbf{U} \mathbf{\Sigma} \mathbf{V}^T$$

- **$\mathbf{U}$ (Left Singular Vectors):** An $m \times m$ orthogonal matrix. Its columns are the eigenvectors of $\mathbf{A}\mathbf{A}^T$.
    
- **$\mathbf{\Sigma}$ (Singular Values):** An $m \times n$ diagonal matrix. The non-zero entries on the diagonal are the square roots of the eigenvalues of $\mathbf{A}^T\mathbf{A}$ (or $\mathbf{A}\mathbf{A}^T$).
    
- **$\mathbf{V}^T$ (Right Singular Vectors):** An $n \times n$ orthogonal matrix. Its columns (the rows of $\mathbf{V}^T$) are the eigenvectors of $\mathbf{A}^T\mathbf{A}$.
### Practical Use: Reduced SVD

In machine learning, we often use **Truncated SVD** to compress data. Instead of keeping all singular values, we keep only the top $k$ values. This is how you remove "noise" from a dataset while keeping the signal.