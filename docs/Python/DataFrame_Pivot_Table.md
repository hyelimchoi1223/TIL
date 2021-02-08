---
title: DataFrame Pivot_Table
parent: Python
has_children: false
---
# Pivot_table
[Pivot](https://velog.io/@hyelimchoi1223/Python-DataFrame-Pivot)과 비슷하게 테이블을 만드는 함수. 더 다양한 기능을 제공.

## 정의
> pivot_table(values=None, index=None, columns=None, aggfunc='mean', fill_value=None, margins=False, dropna=True, margins_name='All', observed=False)

* values : aggfunc로 계산될 데이터.
* aggfunc : values를 계산할 연산자를 넣어준다. 기본값은 mean(평균)
* fill_value : NaN인 데이터에 채워줄 값.
  
## 예제
```
| Subject  | Name       | Score      | Sex      |
| -------- | ---------- | ---------- | -------- | 
| Math     | billy      | 80         | male     |
| English  | billy      | 90         | male     |
| Math     | Chris      | 50         | male     | 
| English  | Chris      | 90         | male     |
| Math     | Ann        | 90         | female   | 
| English  | Ann        | 90         | female   |

```
성별 과목 평균을 구해보는 코드.
```python
import pandas as pd
import numpy as np
df = pd.DataFrame({'Subject': ['Math', 'English', 'Math', 'English', 'Math', 'English'],
                   'Name': ['billy', 'billy', 'Chris', 'Chris', 'Ann', 'Ann'],
                   'Score': [80, 90, 50, 90, 90, 90],
                   'Sex': ['male', 'male', 'male', 'male', 'female', 'female']})

df = df.pivot_table(values='Score', index=['Sex'], columns=[
    'Subject'], aggfunc=np.mean)
print(df)
```
```
Subject  English  Math
Sex                   
female        90    90
male          90    65 
```
_더 많은 예제는 [pandas document](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.pivot_table.html) 참고_

## pivot과의 차이점
index와 value는 여러개가 올 수 있다. pivot보다 더 다양한 기능을 제공한다.