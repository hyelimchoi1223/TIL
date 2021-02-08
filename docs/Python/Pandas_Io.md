---
title: Pandas IO 함수
parent: Python
has_children: false
---
# Pandas io 함수

# 1. read_csv
## 정의

> read_csv(filepath, sep=' , ', ...)

- filepath : 가져올 파일 경로, http, ftp 등 URL도 가능
- sep : 기본값은 ',', 데이터의 구분자

_더 많은 매개변수는 [pandas document](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_csv.html) 참고_
## 예제
```python
import pandas as pd

result = pd.read_csv("/user/download/testData.csv")
```
구분자가 tab인 파일 불러오기
```python
result = pd.read_csv("/user/download/testData.tsv", sep="\t")
```
# 2. to_csv
## 정의

> to_csv(filepath, sep=' , ', ...)

- filepath : 가져올 파일 경로, http, ftp 등 URL도 가능
- sep : 기본값은 ',', 데이터의 구분자

_더 많은 매개변수는 [pandas document](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_csv.html?highlight=to_csv#pandas.DataFrame.to_csv) 참고_

## 예제
```python
import pandas as pd

result.to_csv("/user/download/testData(1).csv")
```
구분자가 tab인 파일로 생성하기
```python
result.to_csv("/user/download/testData(2).tsv", sep="\t")
```