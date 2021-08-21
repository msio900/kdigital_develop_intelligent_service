# 0701

## 1. classification

> 주피터 노트북 팁 run all below/run all avobe

1. null이 있는지 없는지 확인...
   1. 

api를 확인하고 학습하면서 할 필요가 있음.

### Logistic Regression

```python
from sklearn.linear_model import LogisticRegression

logR = LogisticRegression() # 모델 초기화
type(logR) # 범주형 모델 이름이 비슷하다고 헷갈리지 말라!! 아예 classification = LogisticRegression
sklearn.linear_model._logistic.LogisticRegression

logR.fit(X_train, Y_train)
C:\Python\Python36\lib\site-packages\sklearn\utils\validation.py:63: DataConversionWarning: A column-vector y was passed when a 1d array was expected. Please change the shape of y to (n_samples, ), for example using ravel().
  return f(*args, **kwargs)
LogisticRegression()

logR.classes_
array([0, 1], dtype=int64)

logR.coef_ # 내가 넣은 항목마다 계수의 갯수가 생김.
array([[-0.84804181, -0.12789375,  0.26294701,  0.00288228]])
# 방정식이 한번 나오게 됨.

logR.score(X_train, Y_train)
0.6946107784431138

```

`probablity` : 

#### [예시]

5명 찬반 투표

- 찬성 : 2--> 2/5
- 반대 : 3 --> 3/5

2/5 + 3/5 = 1

시그모이드 함수

카테고리가 2개 있으면 2개에 대한 의견을 각각 내게 됨.

[사람 A] : 찬성 0.8, 반대 0.2 -> 찬성

[사람 B] : 찬성 0.1, 반대 0.9 -> 반대

후보자 3명,  선거인단 10명

후보자 A

후보자 B

후보자 C

가 : 후보자 A=0.2, 후보자 B=0.5, 후보자 C=0.3

0과 1로 분할 할수 있는 시그모이드 공식

라인 하나를 가지고 이쪽으로 갈 확률 저쪽으로 가까이 갈 확률 두번을 돌리고 그 결과가 합하면 1이 됨.

카테고리가 3개 이상인 경우에도 합은 1이 됨.



logR.coef_ 의 결과 값이.... e의 승수에 있는 연립방정식의 계수로 들어감.

##### 딥러닝에서는 공식 하나가 뉴런 하나

## iris 데이터셋

```python
from sklearn import datasets
iris = datasets.load_iris()
type(iris)
sklearn.utils.Bunch
# 번치 데이터

x = iris.data
y = iris.target
x.shape, y.shape, type(x), type(y)
((150, 4), (150,), numpy.ndarray, numpy.ndarray)
# numpy 데이터 구나!

import numpy as np
np.unique(y)
array([0, 1, 2])
# 유니크 값이 세개...
```

#### 로지스틱 회귀는 직선을 긋고 판별을 함. 순차적으로

직선으로만 표현되서... 어려운 부분을 극복하기 위해 곡선을 사용하는 경우가 많아짐.

