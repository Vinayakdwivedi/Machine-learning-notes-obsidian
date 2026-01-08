While preparing the data for training and evaluation, we normally split the data using a function such as Scikit-Learn’s `train_test_split` . To make sure that the results are reproducible, we use the `random_state` argument, so however many times we split the same data set, we will always get the very same train-test split. And in this sentence lies the potential issue I mentioned before, particularly in the part about _the same data set_.

```How this will affect, let's say your model works fine and is in production. When new data come you try to train your model on old_data + new_data. If you then split the data there is a high chances that the new test split will contain the data on which the model was trained previously, same with training set```

We can calculate the hash of observation and define a particular %, that hash less than that % will be in test data set. For hashing we can use [[CRC]] hashing algorithm .

[[code_implementation]] 
source:- https://towardsdatascience.com/improve-the-train-test-split-with-the-hashing-function-f38f32b721fb/