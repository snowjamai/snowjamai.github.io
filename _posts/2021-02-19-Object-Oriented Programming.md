---
title: "파이썬 Programming"

categories:
- 자연어

tags:
- 파이썬 기초
- 딥러닝
- 자연어
---

***

### 1. comprehension
1. List, Dictionary 등을 빠르게 만드는 기법
    * for + append 보다 속도가 빠름
```
result = [i * 2 for i in range(10)]     # (0 ~ 9) * 2 리스트 생성

result = {str(i): i for i in range(10)}     # Dictionary 생성

result = {str(i) for i in range(10)}        # Set 생성
```
2. if 문을 마지막에 달아 원하는 요소 추가 가능
3. 이중 for문 사용 가능
```
result = [(i, j) for i in range(5) for j in range(i)]
```
4. 다차원 배열 만들기 가능
```
eye = [[int(i == j) for j in range(5)] for i in range(5)]

```
5. Generator
    * __yield__ 가 있는 함수는 generator
    * yield 하는 위치에서 값을 반환
    * 다시 값을 요청 받을 때 yield 다음줄부터 실행
    * Return 될 경우에 StopIteration Error 발생
    * Sequence 전체 생성이 아니므로 메모리 효율적이므로 매우 큰 데이터 셋을 처리할때 유용
```
def my_rage(stop):
    number = 0
    while number < stop:
    yield number
    number += 1
```

6. Built-in Functions
    * sum([iterable])
    * any([iterable])   #하나라도 참
    * all([iterable])   #모두 참
    * max([iterable])
    * min([iterable])

7. zip
    * 두개 이상의 순환 가능한 객체를 앞에서부터 한번에 접근할 때 사용

8. enumerate
    * For문이 Sequence를 돌 때 그 index가 필요할때 사용
    * enumerate()을 사용하면 인덱스와 값을 동시에 참조
    * Generator는 List형태로 출력하기 위해 list로 변화 필요

9. Lambda Function
    * 함수의 이름 없이 빠르게 만들어 쓸 수 있는 익명 함수
    * lambda [param1],[param2],...:[expression] 형태로 사용
    * 여러줄을 쓸 수 없음
    * 복잡한 함수 lambda로 작성할 시 가독성이 하락하고 이름이 존재하지 않는 함수가 생성되므로 공식적으로 권장하지 않으나 많이 씀

10. map

    * 각 요소에 function 함수를 적용하여 반환


11. filter
    * 각 요소에 function 함수를 적용하여 참이 나오는 것만 반환