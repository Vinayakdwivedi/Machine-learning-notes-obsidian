
1) We can remove whole row which has the null value.
2) We can remove the row which has the null value.
3) Fill the empty value with mean or median.
It is better to remove the row if it has more than 1 missing field.
```
df.dropna(subset = 'df[column_1]')   #1
df.drop("colums", axis = '1')        #2
S = df["column"].median()            #3
df["column_x"].fillna(S, inplace = True)
```
This is called as imputation 
3 option ✅static data ❌for changing data
Imputation for changing data-
we have a class in scikit-learn called **SimpleImputer** 
```
from sklearn.imputer import SimpleImputer
imputer = SimpleImputer()
age = df[[age]]
imputer.fit(age)
X = imputer.transform(age)
```
