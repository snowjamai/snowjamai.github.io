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
```bash 
git pull origin master
bash preprocess.sh dump-raw-wiki
```
### 3. Conditional Probability
$ P(x|y) = \frac{P(x,y)}{P(y)} $

임베딩을 위해서는 말뭉치(학습 데이터)가 필요
1. 직접 말뭉치를 만들기
2. 웹 문서에 대한 스크래핑(scraping)
3. 공개된 말뭉치 데이터 받아오기

### 4. 진화 과정을 시각화하는 방법
1. 한국어 위키 백과에 대한 raw data 다운
```bash 
git pull origin master
bash preprocess.sh dump-raw-wiki
```
### 5. 기호 회귀 문제를 푸는 방법

### 6. 지능형 로봇 제어기를 만드는 방법