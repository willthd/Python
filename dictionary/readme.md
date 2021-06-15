## dictionary

대응 관계를 나타낼 수 있는 자료형. 이를 연관 배열(Associative array) 또는 해시(Hash)라고 한다.

```python
# 1. 생성
dict_ = dict()
dict2_ = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}

# Tuple List로부터 dict 생성
# key가 이름, val이 나이
persons = [('김기수', 30), ('홍대길', 35), ('강찬수', 25)]
mydict = dict(persons)
 
# mydict.get('홍대길')과 동일, mydict.get('홍대성') : '홍대성' 없으면 None return함
age = mydict["홍대길"]
print(age)   # 35
 
# 2. Key=Value 파라미터로부터 dict 생성
scores = dict(a=80, b=90, c=85)
print(scores['b'])  #90

scores = {"철수": 90, "민수": 85, "영희": 80}
# 3. 수정
scores["민수"] = 88

# 4. 추가
a = {1: 'a'}
# 접근은 list처럼. list는 아래와 같은 방식으로 원소 추가 불가능
a[2] = 'b'
print(a) # {1: 'a', 2: 'b'}

# 5. 삭제
del scores["영희"]
# key, value 모두 삭제
scores.clear()
print(scores)
# {}

# 출력 {'철수': 90, '길동': 95, '민수': 88}
print(scores)

# 6. 읽기
scores["민수"]
# key값이 없으면 위의 방법은 에러 발생하고 아래 방법은 None을 return
scores.get("민수")
# key 값 없을 때 "bar"를 return하도록 설정 가능
scores.get('foo', 'bar')

# 7. sort
# dict.sort()는 없음. 따라서 sorted만 이용
# 파이썬의 사전은 key : value 쌍으로 값이 들어 있으며, 이를 정렬(sort)하면 기본으로 키(key)을 기준으로 오름차순으로 정렬
fruits = { 'apple': 2, 'banana' : 1, 'melon' : 0, 'pear' : 2, 'plum' : 1}
sorted(fruits)
# 결과 : ['apple', 'banana', 'melon', 'pear', 'plum']

# value 기준으로 key를 정리하고 싶으면
sorted(fruits, key=lambda x:fruits[x], reverse=True)
# 결과 : ['apple', 'pear', 'banana', 'plum', 'melon']

# 추가 기능
keys = scores.keys()
# dict_keys(['apple', 'banana', 'melon', 'pear', 'plum'])
vals = scores.values()
# dict_values([2, 1, 0, 2, 1])
items = frutis.items()
# dict_items([('apple', 2), ('banana', 1), ('melon', 0), ('pear', 2), ('plum', 1)])

# dict_keys 등의 객체는 다음과 같이 사용할 수 있다. 리스트를 사용하는 것과 차이가 없지만, 리스트 고유의 함수인 append, insert, pop, remove, sort등의 함수를 수행할 수는 없다.

# key 있는지 조사
a = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}
print('name' in a)
# True
# 이 때, dict는 set을 backing하고 있기 때문에 시간 복잡도 O(1). list의 경우는 O(n)

# list를 key로 지정
genre_count = dict.fromkeys(total_genres)

# defaultdict
from collections import defaultdict
word2id = defaultdict(lambda : 0, a=3)
# key값 없을 때 0 return
word2id['a'] # 3
word2id['c'] # 0
```

