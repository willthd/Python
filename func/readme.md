## func

### 여러 개의 입력값을 받는 함수 만들기

- 튜플

```python
>>> def sum_many(*args): 
...     sum = 0 
...     for i in args: 
...         sum = sum + i 
...     return sum 

```

위에서 만든 sum_many라는 함수는 입력값이 몇 개이든 상관이 없다. `*args`처럼 매개변수명 앞에 `*`을 붙이면 입력값들을 전부 모아서 튜플로 만들어 주기 때문이다.

```python
>>> result = sum_many(1,2,3)
>>> print(result)
6
>>> result = sum_many(1,2,3,4,5,6,7,8,9,10)
>>> print(result)
55
```

</br>

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

</br>

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

</br>

### lambda

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

```python
>>> myList[0]
at 0x811eb2c>
>>> myList[0](3,4)
7
```

```python
>>> myList[1](3,4)
12
```

```python
# 홀수 짝수 판별
>>> is_odd = lambda x: True if x % 2 == 1 else False
>>> is_odd(3)
True
```

 