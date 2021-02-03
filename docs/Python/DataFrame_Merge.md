---
title: DataFrame Merge 함수
parent: Python
has_children: false
---

# Merge

두 개의 DataFrame을 합치는 함수.

## 정의

> merge(right, how=‘inner’, on=None, left_on=None, right_on=None, left_index=False, right_index=False, sort=False, suffixes=(‘_x’, ‘_y’), copy=True, indicator=False, validate=None)

- right : Merge 할 DataFrame
- how : Merge 방식, inner가 기본값
- on : Merge 기준의 컬럼 또는 인덱스 값, 단 두개의  DataFrame에 해당 컬럼이 존재해야 한다.
- left_on : Merge 기준이 되는 왼쪽 DataFrame의 컬럼 또는 인덱스 값
- right_on : Merge 기준이 되는 오른쪽 DataFrame의 컬럼 또는 인덱스 값

## 예제

```python
# user_df DateFrame
UserID | Age | Name
-------------------
1      |  40 | Adam
2      |  28 | Alex
3      |  60 | Billy

===================

# money_df DateFrame
ID     | Money
-------------------
1      | 15000
2      | 8000
3      | 2000
```

```python
>> user_df.merge(money_df, left_on="UserID", right_on="ID")
  UserID | Age | Name | ID | Money
------------------------------------
0 1      |  40 | Adam | 1  | 15000
1 1      |  40 | Adam | 2  | 8000
2 1      |  40 | Adam | 3  | 2000
3 2      |  28 | Alex | 1  | 15000
4 2      |  28 | Alex | 2  | 8000
5 2      |  28 | Alex | 3  | 2000
6 3      |  60 | Billy| 1  | 15000 
7 3      |  60 | Billy| 2  | 8000
8 3      |  60 | Billy| 3  | 2000
```

### 같은 이름의 컬럼명을 가지고 Merge

```python
# user_df DateFrame
ID     | Age | Name
-------------------
1      |  40 | Adam
2      |  28 | Alex
3      |  60 | Billy

===================

# money_df DateFrame
ID     | Money
-------------------
1      | 15000
2      | 8000
3      | 2000
```

```python
>> user_df.merge(money_df) # = user_df.merge(money_df, on="ID")
  UserID | Age | Name | ID | Money
------------------------------------
0 1      |  40 | Adam | 1  | 15000
1 1      |  40 | Adam | 2  | 8000
2 1      |  40 | Adam | 3  | 2000
3 2      |  28 | Alex | 1  | 15000
4 2      |  28 | Alex | 2  | 8000
5 2      |  28 | Alex | 3  | 2000
6 3      |  60 | Billy| 1  | 15000 
7 3      |  60 | Billy| 2  | 8000
8 3      |  60 | Billy| 3  | 2000
```

### Pandas의 Merge 함수를 이용

```python
>> result_df = pd.merge(user_df, money_df)
>> print(result_df)
  UserID | Age | Name | ID | Money
------------------------------------
0 1      |  40 | Adam | 1  | 15000
1 1      |  40 | Adam | 2  | 8000
2 1      |  40 | Adam | 3  | 2000
3 2      |  28 | Alex | 1  | 15000
4 2      |  28 | Alex | 2  | 8000
5 2      |  28 | Alex | 3  | 2000
6 3      |  60 | Billy| 1  | 15000 
7 3      |  60 | Billy| 2  | 8000
8 3      |  60 | Billy| 3  | 2000
```