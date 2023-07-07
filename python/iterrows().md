# Pandas에서 loc → for문 쓸거야? 행을 순회하는 방법: iterrows()
# **서론**

pandas 라이브러리의 가장 강력한 측면 중 하나는 데이터를 조작하고 분석하는 능력입니다. 그러나 데이터의 각 행을 개별적으로 처리해야 할 경우는 어떨까요? 이때 `iterrows()`라는 함수를 활용하면 됩니다. 이 함수는 pandas DataFrame의 각 행을 효율적으로 순회할 수 있는 방법을 제공합니다.

# 1. `iterrows()` 이해하기

`iterrows()`는 pandas DataFrame의 각 행에 대해 순회하는 함수입니다. (returen: `index` `row`)

```python
for index, row in df.iterrows():
    print(index, row)
```

이 코드는 각 행의 인덱스와 해당 행 데이터를 pandas Series로 출력합니다.

# 2. **`iterrows()`의 장점**

## 편의성

`iterrows()`를 사용하여 행을 순회하는 것은 각 행에 개별적인 연산을 수행해야 할 때 편리합니다. 간결하게 행별 반복을 가능하게 합니다.

## 가독성

`iterrows()`를 사용하면 코드가 파이썬스럽고 이해하기 쉬워집니다. 특히 파이썬의 반복 규칙에 익숙한 사람들에게 유용합니다.

## 유연성

`iterrows()`에서 반환하는 각 행은 Series 객체이므로, 바로 Series 메소드를 사용할 수 있습니다.

## 성능에 대한 참고 사항

`iterrows()`는 편리하지만 항상 최선의 선택이라고는 할 수 없습니다. 대규모 DataFrame을 다룰 때는 벡터화된 연산이나 `apply()` 함수를 사용하는 것이 종종 더 효율적입니다.

## 사용 예시

`iterrows()`를 어떻게 사용할 수 있는지 간단한 예를 보겠습니다. 여러 가지 과일과 그 가격에 대한 정보를 포함하는 DataFrame `df`가 있다고 가정해봅시다:

```python
import pandas as pd

data = {
    '과일': ['사과', '바나나', '체리', '대추'],
    '가격': [1200, 500, 750, 1500]
}

df = pd.DataFrame(data)

for index, row in df.iterrows():
    print(f"{row['과일']}의 가격은 {row['가격']}원입니다.")
```

이 스크립트는 각 과일의 가격을 출력하여, `iterrows()`를 사용하여 각 행의 데이터에 접근하는 방법을 보여줍니다.

## 결론

Pandas의 `iterrows()`는 DataFrame의 각 행을 순회하는 방법을 제공하여, 데이터를 행별로 처리해야 하는 경우에 특히 유용합니다. 그러나 데이터의 크기와 성능에 대한 영향을 고려하여 `iterrows()`나 `apply()` 같은 다른 pandas 함수를 사용할지 결정해야 합니다.
