---
title: DataFrame Fillna 함수
parent: Python
has_children: false
---
# Fillna

NaN을 특정 데이터로 채워줌.

## 정의
> fillna(value=None, method=None, axis=None, implace=False, limit=None, downcast=None)

- value : NaN에 채울 값

## 예제

```python
# result DataFrame
ID     | Money
-------------------
1      | 15000
2      | 8000
3      | 2000
4      | NaN
5      | NaN
6      | NaN
```

```python
>> result.fillna(value=0, inplace=True)
ID     | Money
-------------------
1      | 15000
2      | 8000
3      | 2000
4      | 0
5      | 0
6      | 0
```