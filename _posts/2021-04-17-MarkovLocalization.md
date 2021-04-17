---
title: "Markov Localization"

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
### 1. State Estimation 정의
상태 예측이라는 말로 state란 주변 환경(동적인 객체, 정적인 객체)에 따른 상태를 의미
- 센서 데이터를 받아 직접 관측 불가능한 물리량을 추론
- 센서로는 추정의 일부만 가능 (sensor fusion에 의한 정확도 향상 - lidar + radar)
- 센서 관측값에 대해서는 noise 존재
    

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
```python
$Algorithm Bayes_filter(bel(x_{t-1}), u_{t}, z_{t}):$
    for all x_{t} do
      $ \overline{bel(x_{t})} = \int P(x_{t}|u_{t},x_{t-1}) \cdot bel(x_{t-1}) dx_{t-1} $

```