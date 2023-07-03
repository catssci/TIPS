```python
import pandas as pd

# 예시 DataFrame 생성
data = {'A': [1, 2, 3], 'B': ['apple', 'banana', 'orange'], 'C': [True, False, True]}
df = pd.DataFrame(data)

# DataFrame을 기본 딕셔너리로 변환
dict_data = df.to_dict()

print(dict_data)
```

```python
{'A': {0: 1, 1: 2, 2: 3}, 'B': {0: 'apple', 1: 'banana', 2: 'orange'}, 'C': {0: True, 1: False, 2: True}}
```

- index 제거 **(orient='records')**

```python
import pandas as pd

# 예시 DataFrame 생성
data = {'A': [1, 2, 3], 'B': ['apple', 'banana', 'orange'], 'C': [True, False, True]}
df = pd.DataFrame(data)

# DataFrame을 리스트 형식의 딕셔너리로 변환
list_dict_data = df.to_dict**(orient='records')**

print(list_dict_data)
```

```python
[{'A': 1, 'B': 'apple', 'C': True}, {'A': 2, 'B': 'banana', 'C': False}, {'A': 3, 'B': 'orange', 'C': True}]
```
