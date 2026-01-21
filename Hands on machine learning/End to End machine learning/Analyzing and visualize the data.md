Our mind is very good at finding patterns.
To find patterns we  must first create good visuals of our data and then do the analysis.
### Correlation coefficient
To get better understanding of our data we may find the correlation between attributes and then plot them on the graph.
We can use [[scatter_matrix]] from pandas which will plot correlation between all the attributes of the data

``` python
from pandas import scatter_matrix
attributes = [attribute_1, attribute_2, attribute_3, attribute_4]
scatter_matrix(df[attributes], fig_size = (12,8))
```

