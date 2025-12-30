# Placeholder
1주차 - Model 

### 🎤 발표 핵심

- Model = 함수? 시스템?
- 입력 → 출력 → 파라미터 → Loss
- 학습 vs 추론 차이
- Overfitting / Generalization

### 🔑 키워드

`Model`, `Parameter`, `Loss`, `Training`, `Inference`, `Overfitting`, `Generalization`

## Model은 함수인가? 시스템인가?

-> 둘다 맞다.

시스템이란 : 데이터를 학습하여 특정 작업을 수행하고, 추론이나 문제 해결과 같은 인간과 유사한 지능적 기능을 수행할 수 있도록 설계된 통합된 컴퓨터 프로그램 및 관련 인프라

수학적으로
주어진 데이터를 입력받아 결과를 출력한다는 점에서 함수이다

시스템적으로
입력을 받고 내부 파라미터(특정 동작이나 결과에 영행을 미치는 변수나 설정 값)로 계산을 하여 출력을 내는 하나의 예측 시스템이다

-> 딥러닝에서 말하는 Model은 "파라미터를 가진 함수"이라고 말할 수 있다

https://steelbear.tistory.com/115

## Model의 기본 구성

1. 입력 (INPUT)
데이터 x
이미지,텍스트,수치 등 다양한 방식
모델이 관측하는 정보

2. 파라미터 (Parameter)
가중치(각 입력 신호가 결과 출력에 미치는 중요도를 조절하는 매개변수), 편향(뉴런의 활성화 조건을 결정하는 매개변수)
Model 내부에 존재
AI 학습을 통해 바뀌는 값

-> 학습을 통해 모델이 똑똑해지는 이유는 파라미터가 바뀌기 때문이다.

https://blog.naver.com/jgyy4775/222642220219

3. 출력(Output)
예측값 y
분류, 확률 등 다양한 방식
모델이 내린 결론

4. 손실 함수(Loss)
예측값과 실제값의 차이를 수치화
모델이 얼마나 틀렸는지를 알려줌
이를 기반으로 파라미터를 수정하게 된다
https://modulabs.co.kr/blog/loss-function-machinelearning


## Training vs Inference

**학습(Training)**
목적 -> 파라미터를 업데이트

학습과정 (Training Process)

1. 순전파(Forward Propagation)
입력값을 네트워크에 전달하여 각 층을 거쳐 예측값(prediction)을 계산한다
2. 로스 함수 계산 (Loss Function)
예측값과 실제 값(정답)을 비교하여 오차(loss)를 계산한다
3. 역전파 (Backpropagation)
로스 함수에서 구한 오차를 네트워크의 각 층으로 역으로 전달하면서 기울기(gradient)를 계산한다
4. Parmeter 업데이트
역전파를 통해 계산된 기울기(gradient)를 이용해 파라미터를 수정한다
5. 반복
순전파 → 로스 계산 → 역전파 → 가중치 업데이트 과정을 여러 번 반복하여 모델의 성능을 개선해 나간다
https://salmon1113.tistory.com/64

**추론(Inference)**
목적 -> 현재 데이터에 대해서 해당 모델이 원하는 작업을 수행해 주는 것

특징

파라미터 고정
Loss 계산 X
순전파(Forward Propagation)만 일어난다
https://manchann.tistory.com/16

## Overfitting & Generalization

**과적합(Overfitting)**
모델이 훈련 데이터셋의 경향성을 너무 잘 반영해서 생기는 문제
훈련에 사용된 데이터셋이 실제 데이터들을 완벽히 반영할 수 없기 때문에 문제가 된다
-> 모델이 데이터들을 이해한 상태가 아닌 암기한 상태
https://all-the-meaning.tistory.com/28

**일반화(Generalization)**
학습된 모델이 훈련 데이터를 넘어서 새롭고 보이지 않는 데이터에 대해 정확하게 예측할 수 있는 능력
과적합과 과소적합 두 문제를 적절히 조절함으로써, 훈련 데이터와 유사한 새로운 데이터에서도 잘 작동할 수 있어야 한다
https://www.gyata.ai/machine-learning/machine-learning-generalization

## Overfitting이 발생하는 이유

모델이 너무 복잡함
데이터가 적음
규제가 없음 (Regularization)

Regularization(규제화)
과적합(Overfitting)을 방지하기 위해 사용되는 기법
모델의 복잡도를 제한하여 과적합 문제를 완화

## Generalization(일반화)을 높이는 방법

데이터 증가
규제화
Dropout
Early Stopping

**Dropout**
학습 단계에서 뉴런을 무작위로 선택하여 일시적으로 비활성화 하는 방식
모든 뉴런의 성능을 전체적으로 높일 수 있다

**Early Stopping**
학습 반복 횟수가 늘어날수록 학습셋에 대한 오차는 줄어들지만, 검증셋의 오차가 증가하며 과적합이 일어날 수 있다
이전 반복횟수와 비교해서 오차가 증가하면 과적합이 발생하기 전에 학습을 멈춘다
https://wegonnamakeit.tistory.com/9
