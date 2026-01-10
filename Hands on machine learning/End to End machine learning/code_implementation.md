
```
def hashed_train_test_split(df, index_col, test_size=0.2):
    """
    Train-test split based on the hash of the unique identifier.
    """
    test_index = df[index_col].apply(lambda x: crc32(np.int64(x)))
    test_index = test_index < test_size * 2**32

    return df.loc[~test_index], df.loc[test_index]
```
