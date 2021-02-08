---
title: DataFrame Pivot
parent: Python
has_children: false
---
# Pivot
주어진 인덱스, 컬럼, value로 DataFrame을 다시 정의.
아래 그림과 같은 형태로 DataFrame이 만들어진다.
![](https://images.velog.io/images/hyelimchoi1223/post/27ca3e4a-19ab-4e97-9e2f-d203bd274889/E3C7C1D9-93B6-405B-ACB0-63DF9D6971AD.jpeg)

## 정의

> pivot(index=None, colums=None, values=None)

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
```python
import pandas as pd

df = pd.DataFrame({'Subject': ['Math', 'English', 'Math', 'English', 'Math', 'English'],
                   'Name': ['billy', 'billy', 'Chris', 'Chris', 'Ann', 'Ann'],
                   'Score': [80, 90, 50, 90, 90, 90],
                   'Sex': ['male', 'male', 'male', 'male', 'female', 'female']})

df = df.groupby(['Sex', 'Subject']).size().reset_index(name="count")
print(df)
```
```
      Sex  Subject  count
0  female  English      1
1  female     Math      1
2    male  English      2
3    male     Math      2

```
_더 많은 예제는 [pandas document](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.pivot.html) 참고_

## pivot_table과의 차이점
[pivot_table](https://velog.io/@hyelimchoi1223/Python-DataFrame-Pivottable)은 연산자를 넣어서 계산하면서 pivot table 생성이 가능하다. 더 다양한 기능을 제공한다.