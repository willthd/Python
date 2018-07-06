## func

### 여러 개의 입력값을 받는 함수 만들기

- 튜플

```python
>>> def sum_many(*args): 
...     sum = 0 
...     for i in args: 
...         sum = sum + i 
...     return sum 
... 
>>>
```

위에서 만든 sum_many라는 함수는 입력값이 몇 개이든 상관이 없다. `*args`처럼 매개변수명 앞에 `*`을 붙이면 입력값들을 전부 모아서 튜플로 만들어 주기 때문이다.



실제로 이 함수를 직접 입력해 보자.

```python
>>> result = sum_many(1,2,3)
>>> print(result)
6
>>> result = sum_many(1,2,3,4,5,6,7,8,9,10)
>>> print(result)
55
```



------

- 집합

```python
>>> def func(**kwargs):
...     print(kwargs)
...
```

그리고 이 함수를 다음과 같이 사용해 보자.

```python
>>> func(a=1)
{'a': 1}
>>> func(name='foo', age=3)
{'age': 3, 'name': 'foo'}
```

func 함수의 인수로 key=value 형태를 주었을 때 입력 값 전체가 kwargs라는 딕셔너리에 저장된다는 것을 알 수 있다.

즉, `**kwargs`는 모든 key=value 형태의 입력인수가 저장되는 딕셔너리 변수이다.



### 매개변수에 초깃값 미리 설정하기

이번에는 조금 다른 형태로 함수의 인수를 전달하는 방법에 대해서 알아보자. 매개변수에 초깃값을 미리 설정해 주는 경우이다. 초기화 시키는 변수는 항상 마지막에 위치

> ※ 앞으로 나올 프로그램 소스에서 >>> 표시가없으면 에디터로 작성하기를 권장한다는 뜻이다.

```python
def say_myself(name, old, man=True): 
    print("나의 이름은 %s 입니다." % name) 
    print("나이는 %d살입니다." % old) 
    if man: 
        print("남자입니다.")
    else: 
        print("여자입니다.")
```

> ※ say_myself 함수는 3개의 입력 인수를 받아서 마지막 인수인 man이 True이면 "남자입니다.", False이면 "여자입니다."를 출력한다.



### global 명령어 이용하기

```python
# vartest_global.py
a = 1 
def vartest(): 
    global a 
    a = a+1

vartest() 
print(a)
```

global은 함수 밖의 변수를 사용하겠다는 뜻. 하지만 함수는 독립적이어야 하므로 되도록 이와 같은 방법은 피한다



### lambda

lambda는 함수를 생성할 때 사용하는 예약어로, def와 동일한 역할을 한다. 보통 함수를 한줄로 간결하게 만들 때 사용한다. 우리말로는 "람다"라고 읽고 def를 사용해야 할 정도로 복잡하지 않거나 def를 사용할 수 없는 곳에 주로 쓰인다. 사용법은 다음과 같다.

> lambda 매개변수1, 매개변수2, ... : 매개변수를 이용한 표현식

한번 직접 만들어 보자.

```python
>>> sum = lambda a, b: a+b
>>> sum(3,4)
7
```

sum은 두개의 인수를 받아 서로 더한 값을 리턴하는 lambda 함수이다. 위의 예제는 def를 사용한 아래 함수와 하는 일이 완전히 동일하다.

```python
>>> def sum(a, b):
...     return a+b
...
>>>
```

그렇다면 def가 있는데 왜 lambda라는 것이 나오게 되었을까? 이유는 간단하다. lambda는 def 보다 간결하게 사용할 수 있기 때문이다. 또한 lambda는 def를 사용할 수 없는 곳에도 사용할 수 있다. 다음 예제에서 리스트 내에 lambda가 들어간 경우를 살펴보자.

```python
>>> myList = [lambda a,b:a+b, lambda a,b:a*b]
>>> myList
[at 0x811eb2c>, at 0x811eb64>]
```

즉, 리스트 각각의 요소에 lambda 함수를 만들어 바로 사용할 수 있다. 첫 번째 요소 myList[0]은 2개의 입력값을 받아 두 값의 합을 돌려주는 lambda 함수이다.

```python
>>> myList[0]
at 0x811eb2c>
>>> myList[0](3,4)
7
```

두 번째 요소 myList[1]은 2개의 입력값을 받아 두 값의 곱을 돌려주는 lambda 함수이다.

```python
>>> myList[1](3,4)
12
```

파이썬에 익숙해질수록 lambda 함수가 굉장히 편리하다는 사실을 알게 될 것이다.