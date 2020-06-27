## Class



```python
class Flight:

    def __init__(self, num):
        print('init')
        super().__init__()
        self._num = num

#    def __new__(cls):
#        print('new')
#        return super().__new__(cls)

    def number(self):
        return 'SN060', self._num
```

생성자로 객체생성을 호출받으면 먼저 `__new__` 를 호출하여 객체를 생성 할당하고, `__new__` 메소드가 `__init__`메소드를 호출하여 객체에서 사용할 초기값들을 초기화하게된다. 따라서 new, init 순서대로 출력됨

일반적으로 파이썬에서 클래스를 만들 시 `__init__` 메소드만 오버라이딩하여 객체초기화에만 이용한다. `__init__` 은 생성자가 아니다.

`__new__` 메소드는 자동으로 실행되므로 제거해도 된다.

위의 예처럼 `_` 언더바 한개는 내부적으로만 사용되는 변수다라고 알리지만, 사실 값을 얻어올수도 있고 할당도 가능한다. 사람들이 코딩컨벤션으로 파이썬을 쓰는 사람들이면 내부적인 변수구나 하고 알고 있을 뿐이다. '_' 언더바 두개로 할 경우 접근 막을 수 있다.

```python
flight = Flight(3)

# 가능, 3
print(flight._num)

# 불가능, __init__()에서 self.__num으로 할 경우
print(flight.__num)
```



