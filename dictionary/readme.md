## dictionary

대응 관계를 나타낼 수 있는 자료형. 이를 연관 배열(Associative array) 또는 해시(Hash)라고 한다.



* 생성

```python
dic = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}
a = dict()
```



**딕셔너리 dic의 정보**

| key   | value       |
| ----- | ----------- |
| name  | pey         |
| phone | 01199993323 |
| birth | 1118        |

 key는 고유값, 변하는 값은 key가 될 수 없다. 따라서 tuple은 key가 될 수 있지만, list는 될 수 없다. 또한 하나의 딕셔너리에 서로 같은 key가 있을 수 없다.(있어도 syntax error는 없지만, key를 통해 value 호출 할 때 랜덤하게 호출 된다)

* 딕셔너리 쌍 추가하기

```python
>>> a = {1: 'a'}
>>> a[2] = 'b'
>>> a
{1: 'a', 2: 'b'}
```

{1: 'a'}라는 딕셔너리에 a[2] = 'b'와 같이 입력하면 딕셔너리 a에 Key와 Value가 각각 2와'b'인 2 : 'b'라는 딕셔너리 쌍이 추가된다



```python
>>> a['name'] = 'pey'
>>> a
{1: 'a', 2: 'b', 'name': 'pey'}
```

딕셔너리 a에 'name': 'pey'라는 쌍이 추가되었다.


```python
>>> a[3] = [1,2,3]
>>> a
{1: 'a', 2: 'b', 'name': 'pey', 3: [1, 2, 3]}
```

Key는 3, Value는 [1, 2, 3]을 가지는 한 쌍이 또 추가되었다.



* 딕셔너리 요소 삭제하기

```python
>>> del a[1]
>>> a
{2: 'b', 'name': 'pey', 3: [1, 2, 3]}
```

위의 예제는 딕셔너리 요소를 지우는 방법을 보여준다. del 함수를 사용해서 del a[key]처럼 입력하면 지정한 key에 해당하는 {key : value} 쌍이 삭제된다.



* 딕셔너리에서 key 사용해 value 얻기

```python
>>> grade = {'pey': 10, 'julliet': 99}
>>> grade['pey']
10

>>> a = {1:'a', 2:'b'}
>>> a[1]
'a'
```



* 함수

  

  #### Key 리스트 만들기(keys)

  ```python
  >>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
  >>> a.keys()
  dict_keys(['name', 'phone', 'birth'])
  ```

  a.keys()는 딕셔너리 a의 Key만을 모아서 dict_keys라는 객체를 리턴한다.

  

  **[파이썬 3.0 이후 버전의 keys 함수, 어떻게 달라졌나?]**

  파이썬 2.7 버전까지는 a.keys() 호출 시 리턴값으로 dict_keys가 아닌 리스트를 리턴한다. 리스트를 리턴하기 위해서는 메모리의 낭비가 발생하는데 파이썬 3.0 이후 버전에서는 이러한 메모리 낭비를 줄이기 위해 dict_keys라는 객체를 리턴해 준다. 다음에 소개할 dict_values, dict_items 역시 파이썬 3.0 이후 버전에서 추가된 것들이다. 만약 3.0 이후 버전에서 리턴값으로 리스트가 필요한 경우에는 "list(a.keys())"를 사용하면 된다. dict_keys, dict_values, dict_items 등은 리스트로 변환하지 않더라도 기본적인 반복성(iterate) 구문(예: for문)들을 실행할 수 있다.

  dict_keys 객체는 다음과 같이 사용할 수 있다. 리스트를 사용하는 것과 차이가 없지만, 리스트 고유의 함수인 append, insert, pop, remove, sort등의 함수를 수행할 수는 없다.

  

  #### Value 리스트 만들기(values)

  ```python
  >>> a.values()
  dict_values(['pey', '0119993323', '1118'])
  ```

  

  #### Key, Value 쌍 얻기(items)

  ```python
  >>> a.items()
  dict_items([('name', 'pey'), ('phone', '0119993323'), ('birth', '1118')])
  ```

  items 함수는 key와 value의 쌍을 튜플로 묶은 값을 dict_items 객체로 돌려준다.

  

  #### Key: Value 쌍 모두 지우기(clear)

  ```python
  >>> a.clear()
  >>> a
  {}
  ```

  

  #### Key로 Value얻기(get)

  ```python
  >>> a = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}
  >>> a.get('name')
  'pey'
  >>> a.get('phone')
  '0119993323'
  ```

  get(x) 함수는 x라는 key에 대응되는 value를 돌려준다. 앞서 살펴보았듯이 a.get('name')은 a['name']을 사용했을 때와 동일한 결과값을 돌려받는다.

  다만, 다음 예제에서 볼 수 있듯이 a['nokey']처럼 존재하지 않는 키(nokey)로 값을 가져오려고 할 경우 a['nokey']는 Key 오류를 발생시키고 a.get('nokey')는 None을 리턴한다는 차이가 있다. 어떤것을 사용할지는 선택이다.

  

  딕셔너리 안에 찾으려는 key 값이 없을 경우 미리 정해 둔 디폴트 값을 대신 가져오게 하고 싶을 때에는 get(x, '디폴트 값')을 사용하면 편리하다.

  ```python
  >>> a.get('foo', 'bar')
  'bar'
  ```

  

  #### 해당 Key가 딕셔너리 안에 있는지 조사하기(in)

  ```python
  >>> a = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}
  >>> 'name' in a
  True
  >>> 'email' in a
  False
  ```



참고

https://wikidocs.net/16 (점프 투 파이썬)