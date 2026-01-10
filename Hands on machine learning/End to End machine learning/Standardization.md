**Standardization** of datasets is a **common requirement for many machine learning estimators** implemented in scikit-learn; they might behave badly if the individual features do not more or less look like standard normally distributed data: Gaussian with **zero mean and unit variance**.

sk-learn class called *Standard Scaler*
**Z score**
$$
z = \frac{x-\mu}{\sigma}
$$
Standardizing using Z-scores solves this by transforming every feature to have:
- **Mean ($\mu$) = 0**
- **Standard Deviation ($\sigma$) = 1**

| Feature | Z-Score (Standardization) | Min-Max (Normalization) |
| :--- | :--- | :--- |
| **Output Range** | Not bounded (usually -3 to 3) | Strictly bounded (usually 0 to 1) |
| **Outliers** | **Robust:** Outliers have less impact. | **Sensitive:** One outlier can "squish" data. |
| **Use Case** | Algorithms assuming Gaussian distribution. | Image processing or Neural Networks. |