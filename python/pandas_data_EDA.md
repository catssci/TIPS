# Data Select (loc)

```python
data.loc[(data['feature1'] == 'aa') & (data['feature2'] > 2), feature_list]
```

# group by

```python
data.loc[(data['feature1'] == 'aa') & (data['feature2'] > 2)].groupby('timestamp').size().reset_index(name = 'new_column')
```

```python
data.loc[(data['feature1'] == 'aa') & (data['feature2'] > 2)].sort_values('feature3').groupby('timestamp').tail(1)
```

# merge

```python
pd.merge(aa, bb, on='yyyymmdd', how = 'left')
pd.merge(aa, bb, on='yyyymmdd', how = 'right')

pd.merge(aa, bb, on='yyyymmdd', how = 'inner')

pd.merge(aa, bb, on='yyyymmdd', how = 'outer')
```
