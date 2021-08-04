---
title: "파이썬 Function"

categories:
- 자연어

tags:
- 파이썬 기초
- 딥러닝
- 자연어
---

***

### 1. Function
1. Function이란? 
    * 코드를 논리적으로 분리, 캡슐화 용도
    * Return 명령이 없을 경우 None 반환
```
def [function]([parameter 1], [parameter 2], ...):
    실행 1
    실행 2
    return [value]

a = function(arg1, arg2)
```
2. 인자로 받은 값을 바로 수정하는것은 권장하지 않음
3. 파이썬에서 상위에 정의된 변수는 언제나 참조 가능
4. 함수 내에서 정의된 변수 이름은 그 함수 내에서만 유효
5. Global Variable : 파일 최상위에 선언되며 다른 파일에서도 볼 수 있음
6. 함수 내에서 상위 변수에 대한 재정의를 하기위한 방법
    * global : 최상위 변수
    * nonlocal : 바로 상위 변수
-> __스파게티 코드의 주 원인으로서 사용하지 않는 것이 좋음__
7. main을 만들고 main내에 local variable을 생성
8. def 내의 변수는 capture하는것이 아니라 상위 함수의 변수의 값이 바뀌게 된다면 print하는 값들도 바뀜
9. closure란?
같은 Argument를 받았을 때, 같은 리턴값을 내뱉는것을 closure라부르고 함수의 완전성(같은 파라미터에 대해서 같은 결과를 출력) __lambda__ 식은 함수의 완전성을 보장하지 않음

```
number = 10

def add(var):
    return var + 2

def multiply(var):
    return var * 2

def factory(function, n):
    def closure(var):
        for _ in range(n):
            var = function(var)
        return var
    return closure

print(factory(add, 4)(10))
print(factory(multiply, 4)(3))


```
10. Decorator(꾸밈자)
    * @를 사용하여 함수를 꾸미는데 사용
    * Class를 사용할 시 Decorator에 인자 추가 가능
    * 함수를 wrapping하기 때문에 기존 함수에 접근 불가
    * functools 라이브러리의 wraps 데코레이터를 사용하면 


<br/>

***

### 2. 재귀함수
1. 자기 자신을 호출하여 반복적으로 수행하는 함수


<br/>


***

### 3. function parameter
1. 인자에 대해 명시적 대입 가능
2. 인자의 기본값 설정 가능 -> 기본값이 설정된 인자는 맨뒤에 붙여서 사용해야함
3. 인자의 개수가 정해져 있지 않을 때는 * (Asterisk)를 사용하여 남은 인자들 Packing 가능 -> 관습적으로 *args 로 사용
4. 남는 인자들은 **kwards를 관습적으로 사용 -> 남는 키워드들에 대해 packing하여 dictionary 형태로 반환 
5. 파라미터의 순서로는 일반 인자 -> 기본값 인자 -> 가변 인자 -> 키워드 가변 인자
6. Sequence에 * 을 붙이면 Unpacking가능
```
-- 리스트, 튜플에 적용 --
def function(a, b, c):
    print(a, b, c)

l = [1, 2, 3]
function(*l)        # 1 2 3

-- Dictionary에 적용 --
def function(var1, var2, **kwargs):
    print(var1, var2, kwargs)

d = {
    'var1': 10,
    'var2':20,
    'var3':30
}
function (**d)      # 10 20 {'var3' : 30}
```
7. 함수에 타입 힌트 제공 가능
    [function]([var]:[type], n : int) -> [Return type]:
8. 타입 힌트는 인터페이스적 알림이므로 타입이 안맞다고 에러를 내진 않음
<br/>


