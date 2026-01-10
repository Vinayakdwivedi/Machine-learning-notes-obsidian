After data preprocessing of the data the data is split in two half's, **training data** and **testing data** . There are several processes for splitting the data-
1.) Use [[train_test_split]] function in sklearn library.
2.) Use [[hashing ]] for unique identification of rows so that there is no intersection between test and training data
3.) The above methods are based on random sampling which can work for large dataset but for smaller datasets we use [[stratified sampling]] 