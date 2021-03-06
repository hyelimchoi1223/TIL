---
title: Numpy Random 함수
parent: Python
has_children: false
---
# Numpy Random 함수

난수를 생성하는 함수이다.

## Random.rand()

0~1 사이의 실수형 난수를 생성한다.

```
import numpy as np

a = np.random.rand(5) # 난수 5개 생성
print(a)
———————————————————
결과값: array([0.73862681, 0.4046173, 0.17409879, 0.03107812, 0.34628294])
```

```
b = np.random.rand(2,3) # 1*3 행렬의 난수 생성
———————————————————
결과값: array([[0.73464077, 0.88753626, 0.40721431],
            [0.58642182, 0.70031375, 0.3199878]])
```

## Random.randint()

low~high 사이의 정수형 난수를 생성한다.

```
c = np.random.randint(1, high=10, size=3)
# = np.random.randint(1,10, size=3)
# 1~10사이의 난수 3개 생성
print(c)
———————————————————
결과값: array([9,5,7])
```

```
d = np.random.randint(1,10, size=(2,3)) # 1~10사이의 2*3행렬의 난수 생성
———————————————————
결과값: array([[3,1,2],
             [4,4,7]])
```
