# 0825 Deep Learning2

## 어제의 복습

* 학습데이터, 검증데이터, 테스트데이터 를 분류하여 사용
  * hold-out과 K-Fold 방식
* 학습을 시키고 평가하는 과정
* 입력값이 많아지면, w(가중치 값), x(변수)가 많아짐.
* activation : 활성함수
  * linear : 회귀
  * sigmoid : 이진분류
  * softmax : 다중분류

## 케라스에서의 개발과정

### sequantial

### model.compile()

* `optimizer` : 보정 작용
* `loss` : 손실함수
  * mse : 회귀
  * binary_crossentropy : 이진분류
  * categorical_crossentropy : 다항분류

### model.fit()

* `epoch` : 전체 학습데이터를 몇회 반복할지 결정합니다.
* `val`

## MNIST와 fashion -MNIST

> 0부터 9까지 숫자를 추축하는 다중 분류 문제를 해결하고자함.

* 28*28 = 784개의 데이터가 들어와서 숫자를 예측한다.
* 결과 10개로 분류

