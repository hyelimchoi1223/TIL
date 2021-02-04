---
title: Sorted 함수
parent: Python
has_children: false
---
# Sorted

iterable 데이터를 정렬하는 함수. 오름차순, 내림차순 설정할 수 있고, 문자열이라면 알파벳 순, 숫자라면 숫자순으로 정렬된다.

## 정의

> sorted(iterable, key=None, reverse=False)

- iterable : 정렬시킬 iterable 데이터(리스트, 딕셔너리, 튜플 등)
- key : 기본값은 None, 순서를 결정하는 함수
- reverse : 기본값은 False, False = 오름차순, True = 내림차순

## 예제

### 기본

```python
data = ["banana", "dragon", "apple", "egg"]
result = sorted(data)
print(result)

['apple', 'banana', 'dragon', 'egg']

```

### key를 이용한 정렬

data 리스트에서 글자 개수가 적은 순으로 정렬

```python
data = ["banana", "dragon", "apple", "egg"]
result = sorted(data, key= str.__len__)
print(result)

['egg', 'apple', 'banana', 'dragon']

```

### 내림차순 정렬

```python
data = ["banana", "dragon", "apple", "egg"]
result = sorted(data, reverse=True)
print(result)

['egg', 'dragon', 'banana', 'apple']

```

## 참고 사이트

- [w3schools](https://www.w3schools.com/python/ref_func_sorted.asp)
- [python문서](https://docs.python.org/3/howto/sorting.html)