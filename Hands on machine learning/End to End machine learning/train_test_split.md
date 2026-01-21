The train_test_split() method is used to split our data into train and test sets. 

First, we need to divide our data into features (X) and labels (y). The dataframe gets divided into X_train,X_test , y_train and y_test. X_train and y_train sets are used for training and fitting the model. The X_test and y_test sets are used for testing the model if it's predicting the right outputs/labels. By default, 25% of our data is test set and 75% data goes into training tests.

``` python
y_train, y_test = train_test_split(X,y ,
                                   random_state=104, 
                                   test_size=0.25,
								   stratify = y, #create stratified sample
                                   shuffle=True)
```

