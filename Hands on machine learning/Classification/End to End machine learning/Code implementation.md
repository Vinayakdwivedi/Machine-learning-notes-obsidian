```
titanic = sn.load_dataset("titanic")
titanic.head()
```
*Output*

| Index | survived | pclass |  sex   | age  | sibsp | parch |  fare   | embarked | class |  who  | adult_male | deck | embark_town | alive | alone |
| :---: | :------: | :----: | :----: | :--: | :---: | :---: | :-----: | :------: | :---: | :---: | :--------: | :--: | :---------: | :---: | :---: |
|   0   |    0     |   3    |  male  | 22.0 |   1   |   0   | 7.2500  |    S     | Third |  man  |    True    | NaN  | Southampton |  no   | False |
|   1   |    1     |   1    | female | 38.0 |   1   |   0   | 71.2833 |    C     | First | woman |   False    |  C   |  Cherbourg  |  yes  | False |
|   2   |    1     |   3    | female | 26.0 |   0   |   0   | 7.9250  |    S     | Third | woman |   False    | NaN  | Southampton |  yes  | True  |
|   3   |    1     |   1    | female | 35.0 |   1   |   0   | 53.1000 |    S     | First | woman |   False    |  C   | Southampton |  yes  | False |
|   4   |    0     |   3    |  male  | 35.0 |   0   |   0   | 8.0500  |    S     | Third |  man  |    True    | NaN  | Southampton |  no   | True  |

```
# Create bins for Age groups: (0-18], (18-40], (40-65], (65-inf)
age_bins = [0, 18, 40, 65, titanic['age'].max() + 1]

# Create a new column 'Age_Group'
titanic['Age_Group'] = pd.cut(titanic['age'], 
                             bins=age_bins, 
                             labels=['Child', 'Young Adult', 'Adult', 'Senior'])

titanic['Age_Group'].head(10)
```

*Output*
![[Pasted image 20251216125210.png]]

```
strat_data = titanic.dropna(subset=['Age_Group']).reset_index(drop=True).copy()
split = StratifiedShuffleSplit(n_splits = 1, test_size = 0.2, random_state=42)
for train_index, test_index in split.split(strat_data, strat_data['Age_Group']):
    train_set = titanic.loc[train_index]
    test_set = titanic.loc[test_index]
train_set.head()

```

![[Pasted image 20251216125555.png]]

Checking the stratifying percentage.
![[Pasted image 20251216125627.png]]