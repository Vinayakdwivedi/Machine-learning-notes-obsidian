Normalization includes Min Max scaling which puts all the value in between 0 to 1 
*formula*
### 1️⃣Min Max scaling
$$
x' = \frac{x - x_{\min}}{x_{\max} - x_{\min}}
$$
### Note
- Sensitive to **outliers**
- Used in **Neural Networks**, **KNN**

## 2️⃣ Mean Normalization
**Idea:**  
Centers data around zero using the mean
### Formula
$$
`x' = \frac{x - \mu}{x_{\max} - x_{\min}}`
$$
Where:
- μ = mean  
### Notes
- Less common
- Useful in **gradient descent intuition**

## 3️⃣ Z-Score Normalization (Standardization)

**Idea:** 
Centers data at zero with unit variance

### Formula

`x' = \frac{x - \mu}{\sigma}`

Where:
- σ\sigmaσ = standard deviation
### Result
- Mean = 0
- Std Dev = 1
### Notes

- Most widely used
- Works well with **Linear Regression**, **Logistic Regression**, **SVM**

## 4️⃣Robust Scaling (Outlier-Resistant)
**Idea:** 
Uses **median** and **IQR** instead of mean & std
### Formula
$$
`x' = \frac{x - \text{Median}}{\text{IQR}}`
$$
Where:
$$
IQR=Q3−Q1
$$​
### Note
- Best when **outliers exist**
- Used in real-world messy data

## 5️⃣Robust Scaling (Outlier-Resistant)
**Idea:** Uses **median** and **IQR** instead of mean & std
### Formula
$$
`x' = \frac{x - \text{Median}}{\text{IQR}}`
$$
Where:
$$
IQR=Q3−Q1\text{IQR} = Q_3 - Q_1IQR=Q3​−Q1​
$$
### Notes
- Best when **outliers exist**
- Used in real-world messy data