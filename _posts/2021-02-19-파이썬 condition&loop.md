---
title: "파이썬 condition과 loop"

categories:
- 자연어

tags:
- 파이썬 기초
- 딥러닝
- 자연어
---

***

### 1. if
1. 조건이 만족될 경우 실행
2. 들여쓰기와 : 를 이용하여 구문을 구분
3. if, elif, else로 구현

```
if 조건1 :
    실행 1
elif 조건2 :
    실행 2
else:
    실행 3
```
4. if문에서 "" = 0 = Flase = None 모두 False로 판단
5. 비교 연산자 및 논리 연산자를 사용
6. 삼항 연산자 사용 가능
```
value = 32

>>> "odd" if value % 2 else "even"
'even'
```

<br/>

***

### 2. Loop
1. 반복해서 구문을 수행하고 들여쓰기와 : 를 사용하여 구문을 구분
2. 파이썬의 For문은 주어진 객체를 순환하는 개념
3. for [Element] in [Iterable]의 형태로 사용
    * for i in range(숫자): -> 0부터 숫자 __미만__ 까지 순환
    * for i in range(숫자1, 숫자2): -> 숫자1부터 숫자2 __미만__ 까지 순환
    * for i in range(숫자1, 숫자2, step): ->
    숫자1부터 숫자2 __미만__ 까지 step씩 넘어가며 순환
4. 모든 순환 가능한 객체는 for문 적용이 가능
5. break로 for문을 빠져나가고 continue로  for문을 뛰어넘는것이 가능
6. for문 반복이 완전하게 끝나면 실행될 블락으로 else: 를 사용 가능 -> break나 exception등이 일어나도 완전하게 끝난게 아니므로 else문으로 들어가게됨

<br/>


***

### 3. Packing 과 Unpacking
1. 패킹 : 여러개의 데이터를 묶는것
2. 언패킹 : 묶인 데이터를 푸는것
3. _ : '_' 자체도 변수이지만 관습적으로 사용하지 않는 변수들에 사용
4. Asterisk를 사용하여 남는 요소들 저장 가능
start, *b, end = List -> 첫 인덱스는 start, 마지막 인덱스는 end에 들어가고 나머지는 b에 list로 저장됨

<br/>

### 4. Dictionary
1. 맵핑을 위한 데이터 구조로서 '{}'를 이용하여 dictionary 표현
2. 완전한 불변 타입(불변 타입 안의 불변타입)일 경우 dictionary의 Key로 사용 가능 -> Hashable 할 경우 Key로 사용 가능
3. {Key1:Value1, Key2:Value2, ...} 식으로 사용
4. Value로는 아무 객체나 가능
5. Key는 중복이 불가능하며 같은 Key가 들어온다면 값이 덮어 씌워짐
6. Dictionary.items()를 이용해서 Dictionary의 Key와 Value를 Tuple List로 반환
7. dictionary.keys()를 이용하여 모든 Key들을 List로 반환
8. dictionary.values()를 이용하여 모든 value들을 List로 반환
9. Hashing으로 구현되어 Indexing이 O(1)
<br/>

### 5. Set
1. Dictionary의 Key만 모여있는 형태
2. {}형태를 사용하지만 : 이없다면 set으로 인식
3. 중복된 요소 추가는 불가
4. s.remove()를 이용하여 요소 삭제시 존재하지 않는 요소는 에러 발생 -> discard() 를 쓰게 된다면 존재하지 않는 요소가 있더라도 error 발생 안됨
5. s.update()로 중복을 무시하며 여러 요소 추가
6. s.clear()로 비움
7. 수학적 집합 연산자 존재
    * & 교집합
    * | 합집합
    * '-' 차집합
    * ^ 배타적 합집합

### 6. frozenset
1. set의 불변타입
2. List -> Tuple 과 같이 set -> frozenset
3. 불변타입이므로 key값으로 사용 가능







