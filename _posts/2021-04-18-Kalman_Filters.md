---
title: "Kalman Filters"

categories:
- 차량 인공지능

tags:
- 자동차
- 위치 추정
- 확률

use_math: true
comments: true
---

***
### 1. Kalman Filter 정의
베이즈필터의 개념을 적용한 알고리즘
- 연속된 공간에 적용한 알고리즘
    

### 2. Localization
대표적인 확률을 이용한 state estimation 기법으로서 확률론을 통한 state estimation의 불확실성을 해소
- beilief distribution을 계산하여 확률적 계산 진행
- Bayes Filte를 사하여 localization 진행

### 3. Conditional Probability
1. $ P(x|y) = \frac{P(x,y)}{P(y)} $
2. 만약 x와 y가 독립일 경우 $ P(x|y) = P(x)


### 4. Bayes Rule
1. 사전확률(prior) P(x)
    - 사건 y가 일어나기 전 x가 일어난 확률
2. 증거(evidence) P(y)
    - 사후확률을 구하기위해 발생한 사건 y의 확률
3. 사후확률(posterior)
    - $ P(x|y) = \frac{P(y|x) \cdot P(x)}{P(y)} $
    - 사건 y가 일어났을 떄, 사건 x가 발생할 확률
    - 센서가 어떠한 값을 측정했을때(사건 y) 차량이 존재하고 있을 state(사건 x)


### 5. Probabilistic Generative Laws
1. Completeness of a State
    - 현재의 state가 과거의 state에 대한 정보를 다 가지고 있다는 가정
  
2. State가 complete하다 가정할 때, 현재가 모든 정보를 가지고 있으므로
- $ P(x_{t}|x_{0:t-1},z_{1:t-1}, u_{1:t}) = P(x_{t}|x_{t-1},y_{t}) $
- $ P(z_{t}|x_{0:t-1},z_{1:t-1}, u_{1:t}) = P(z_{t}|x_{t}) $


### 6. Belief Distributions
관측했던 현재까지의 데이터와 현재까지 행동한 데이터를 이용한 현재 상태에 대한 사후 확률값이며 식은 아래와 같음
$ bel(x_{t}) = P(x_{t}|z_{1:t},u_{1:t}) $

현재까지 관측한 데이터와 바로 직전까지 행동한 데이터를 이용한 상태 예측에 대한 식은 다음과 같음
$ \overline{bel(x_{t})} = P(x_{t}|z_{1:t},u_{1:t}) $

### 7. Bayes Filter Algorithm
1. 특징
    1. 확률 기반의 recursive filter
    2. 이전 상태와 제어값을 이용하여 현재 state를 예측
    3. Bayes rule을 이용한 센서 입력값을 현재 state에 update

2. 방법
    1. 물리 모델을 이용한 Prediction 
       - 물리적 특성(속도)을 이용한 현재 상태에 대한 추정
    2. 센서값을 이용한 예측
        - 센서(GPS)를 이용한 현재 위치 추정

