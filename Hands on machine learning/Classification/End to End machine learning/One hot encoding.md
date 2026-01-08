```
from sklearn.preprocessing import OneHotEncoding
encoding = OneHotEncoding()
x = encoding.fit_transform(df[catagorical_colm])
```
When to use One-Hot Encoding (OHE):

- **[Nominal Data](https://www.google.com/search?q=Nominal+Data&oq=why+to+prefer+onehot+encoding+over+ordinal+encoding&gs_lcrp=EgZjaHJvbWUyBggAEEUYOTIHCAEQIRifBdIBCTIwMjc3ajBqN6gCALACAA&sourceid=chrome&ie=UTF-8&mstk=AUtExfDfkKewVPWYOMdM3y7c8RlisY-1-oZls_vVHyRbyI9WSQfgs3u5_YDIWE5I6WAfGo0kPZ4UjF35ydTfDp7JJkLYJkFSFAoDbrTDD4_u_JMiarHWTAApT6kHlmKNGyzpzpLVs0TjoOaMoFyi3wbI0sf6KabHJbW3JYzEHxFgxcJGaBQ&csui=3&ved=2ahUKEwj038m-zcuRAxVnT2cHHaroCcAQgK4QegQIAxAB):** For features like colors (Red, Green, Blue), countries, or types, where no category is inherently greater than another.
- **To Avoid [Ordinality](https://www.google.com/search?q=Ordinality&oq=why+to+prefer+onehot+encoding+over+ordinal+encoding&gs_lcrp=EgZjaHJvbWUyBggAEEUYOTIHCAEQIRifBdIBCTIwMjc3ajBqN6gCALACAA&sourceid=chrome&ie=UTF-8&mstk=AUtExfDfkKewVPWYOMdM3y7c8RlisY-1-oZls_vVHyRbyI9WSQfgs3u5_YDIWE5I6WAfGo0kPZ4UjF35ydTfDp7JJkLYJkFSFAoDbrTDD4_u_JMiarHWTAApT6kHlmKNGyzpzpLVs0TjoOaMoFyi3wbI0sf6KabHJbW3JYzEHxFgxcJGaBQ&csui=3&ved=2ahUKEwj038m-zcuRAxVnT2cHHaroCcAQgK4QegQIAxAD) Bias:** Prevents algorithms from assuming a hierarchy (e.g., Blue=3 is "more" than Red=1).
- **For Models Assumed to be Sensitive to Order:** Works well with linear models, logistic regression, and neural networks, allowing them to learn separate weights for each category.