# Python

* 입력 받기

```python
"""
Input
5
1 2
3 4
2 6
4 6
5 7
"""

# 방법 1
# stdin.readline()의 경우 개행문자까지 읽기 때문에 len()으로 구하면 +1됨
from sys import stdin
a = int(stdin.readline())
for i range(a):
  b, c = map(int, stdin.readline().split())

  
# 방법 2
# stdin.readline() 대신 input() 활용
# 방법 1이 더 빠름
```

</br>

* 출력

```python
# java에서 System.out.println()과 동일
print("adslkfjl")

# java에서 System.out.print()와 동일
print("adslkfjl", end='')
```

</br>

* map

  list의 각 element에 함수를 적용시켜 결과를 반환

```python
# 각 원소의 제곱 값 출력
items = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x**2, items))

# 결과
# [1, 4, 9, 16, 25]
```

</br>

* filter

  list의 각 element에서 어떤 조건에 일치하는 값만 반환


```python
# 리스트에서 홀수만 출력
is_odd = list(filter(lambda x: x%2 == 1, items))

# 결과
# [1, 3, 5]
```


</br>

* reduce

  list의 각 element끼리 연산할 때 사용

```python
# 리스트의 원소들 간의 합 출력
from functools import reduce

sum = reduce((lambda x,y : x+y), [x for x in range(101)])

# 결과
# 5050
```


</br>

* sort


```python
# 숫자는 오름차순, 문자는 알파벳순으로 정렬. 원본 정렬되어 변환
list.sort()

# sort된 list를 return. 원본 변환 x
sorted(list)

# 원소들을 거꾸로 뒤집는 것 뿐. 원본 변환
list.reverse()

# 원소들은 뒤집어 return 하지만, list()로 한 번감싸야 함. 원본 변환 x
reversed(list)
list[::-1]

# 특정 기준으로 정렬 할 때 key 사용. sorted도 마찬가지
list.sort(key=lambda x:x[0])

# 두 가지 기준으로 정렬 할 때, 앞의 것이 우선 기준. sorted도 마찬가지
list.sort(key = lambda x: (x[0], x[1]))

# 이 때 x[0]에 의해선 reverse로 x[1]에 의해선 정방향으로 구하고 싶다면
list.sort(key = lambda x: (x[0], -x[1]), reverse=True)

# 역순으로 배열
list.sort(key = lambda x: x[0], reverse=True)
```

</br>

* Indexing, 인덱싱

```python
a = "12345"
a[::-1]

# 출력 결과
# 54321
```

</br>

* String, 문자열

```python
# 아래 경우 모두 s 원본 변경 x. return 값만 변경
# 대문자 
s.upper()

# 소문자
s.lower()

# 앞 글자만 대문자
s.caplitalize()

# 거꾸로
s[::-1]

# list와 string
char = list('hello')
char
# 출력 : ['h', 'e', 'l', 'l', 'o']

# string to list
words = "python은 프로그래밍을 배우기에 아주 좋은 언어입니다."
words_list = words.split()
words_list
# 출력 : ['python은', '프로그래밍을', '배우기에', '아주', '좋은', '언어입니다.']

# list to string
time_list = ['10', '34', '17']
':'.join(time_list)
# 출력 : '10:34:17'
```

</br>

* for문, 값과 index 함께 나타내기


```python
  arr = [2, 7, 10]
  for idx, val in enumerate(arr):
  	print(idx, val)
  	
  # 만약 enumerate에서 두 번째 인자를 줄 경우, idx는 두 번째 값(여기선 5)부터 시작
  for idx, val in enumerate(arr, 5):
    print(idx, val)
```

</br>

* string에서 ==와 is의 차이

```python
a = "pub"
b = ''.join(["p", "u", "b"])

# a == b일 경우 True. 값을 비교
# a is b일 경우 False. 객체 자체를 비교
```

 </br> 

* for문, 반복문

```python
for i in range(10, 7, -1):
	print(i)
	
# 출력 결과
# 10
# 9
# 8

# for문 내에서 index 변화 불가능

'''
for i in range(10):
	if i == 3:
		i = 8
	print(i)
'''

i = 0
  while i < 10:
  	if i == 3:
  		i = 8
      i += 1
  	print(i)
  	i += 1	# 꼭 추가
    
    
# list 내부에서 for문 활용하기
modified_numbers = [0 if number % 2 == 0 else 1 if number % 3 == 0 else number for number in numbers]
```


</br>

* format

```python
# format
print('Case #{}: {} + {} = {}'.format(t+1, A, B, A+B))
```

</br>

* List

```python
# 사이즈 1000인 리스트 선언
a = [0] * 1000

# 값의 index 찾기
a.index(값)

# list의 경우 비어있으면 if문에서 false로 사용
# list.isempty()는 not list와 동일
if not seq:
if seq:

# list 읽을 때 주의
# 1은 안되고, 2는 됨
# 1
a = []
a[0] = 1
print(a[0])

# 2
a = []
a.append(1)
print(a[0])
```

</br>


* 소수점

```python
# 소수점 표현 1, 소수점 4째 자리
"{0:0.4f}".format(y)

# 소수점 표현 2, 3.4213
"%0.4f" % 3.42134234
```


</br>


* 몫, 나머지

```python
# 몫만 구하기
5//3

# 나머지만 구하기
5%3
```

</br>

* stack, queue, deque

```python
# 스택
stack = []
# 마지막에 삽입
stack.append(1)
stack.append(2)
stack.append(3)
# 마지막에 pop
stack.pop() # 3
stack.pop() # 2
stack.pop() # 1 

# 큐
queue = []
queue.append(1)
queue.append(2)
queue.append(3)
queue.pop(0) # 1
queue.pop(0) # 2
queue.pop(0) # 3


# 큐, 덱을 이용함, 큐의 경우 앞으로 한칸 씩 값을 옮겨야 하기 때문에 시간 복잡도 O(n)되기 때문
# (deque는 double ended queue의 약자)
from collections import deque
dq = deque()
# 마지막에 삽입
dq.append(1)
dq.append(2)
# 처음에 삽입
dq.appendleft(4)
# 마지막에 pop
dq.pop() # 1
# 처음에 pop
dq.popleft() # 4
dq.popleft() # 2

# list를 deque로 변환
dq = Deque(list_)
```

</br>

* Dictionary

  Hash Table이랑 동일 개념

```python
# 생성
dict_ = dict()

# 1. Tuple List로부터 dict 생성
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
scores["민수"] = 88   # 수정

# 4. 추가
scores["길동"] = 95   # 추가

# 5. 삭제
del scores["영희"]

# 출력 {'철수': 90, '길동': 95, '민수': 88}
print(scores)

# 6. 읽기
v = scores["민수"]

# 7. sort
# dict.sort()는 없음. 따라서 sorted만 이용
# 파이썬의 사전은 key : value 쌍으로 값이 들어 있으며, 이를 정렬(sort)하면 기본으로 키(key)을 기준으로 오름차순으로 정렬
fruits = { 'apple': 2, 'banana' : 1, 'melon' : 0, 'pear' : 2, 'plum' : 1}
sorted(fruits)
# 결과 : ['apple', 'banana', 'melon', 'pear', 'plum']
sorted(fruits.keys())
# 결과 : ['apple', 'banana', 'melon', 'pear', 'plum']

# value 기준으로 key를 정리하고 싶으면
sorted(fruits, key=lambda x:fruits[x], reverse=True)
# 결과 : ['apple', 'pear', 'banana', 'plum', 'melon']

# 8.추가
keys = scores.keys()
vals = scores.values()
```

</br>

* class

```python
class Calculator:
    def __init__(self, val):
        self.result = val

# self는 parameter로 받지 않음, val 없으면 self.result의 초기값만 정해주면 됨
a = Calculator(3)
print(a.result)
# 출력 : 3
```

</br>

* 전역 변수

```python
# 함수 내에서 전역 변수 사용할 경우 global 사용
a = 3

def f1(a):
	global a
	a = 5

f1(a)
print(a)
# 5출력. global 안쓰면 3 출력


# parameter가 object(str제외)일 때는 global 사용하지 않아도 값 변경 되더라?...

a = [0, 1, 2]
def f2(a):
  a[0] = 10

f2(a)
print(a[0])
# 10 출력
```

</br>

* 정수 max, min

```python
import sys

t1 = sys.maxsize
t2 = sys.maxsize+1 #이것도 type int. max값이 있지만 int 타입으로 더 커질 수 있기 때문에 큰 의미 없음
t3 = -sys.maxsize-1 # 최소값(마찬가지로 더 작아질 수 있음)

print(t1)
print(t2)
print(type(t1))
print(type(t2))

# 출력
# 9223372036854775807
# 9223372036854775808
# <type 'int'>
# <type 'int'>
```

</br>

* 최빈값 구하기

```python
from collections import Counter

colors = ['red', 'blue', 'red', 'green', 'blue', 'blue']
cnt = Counter(colors)
# cnt 출력
# Counter({'blue': 3, 'red': 2, 'green': 1})

cnt.keys()
# 출력 : dict_keys(['red', 'blue', 'green']). 접근하려면 list()한다음 접근

cnt.values()
# 출력 : dict_values([2, 3, 1])

cnt.most_common()
# 출력 : (('blue', 3), ('red', 2), ('green', 1))
# 따라서 아래 가능
for key, value, in cnt.most_common():
    print(key, value)
    
cnt.items()
# 출력 : dict_items([('red', 2), ('blue', 3), ('green', 1)])

cnt.elements()
# 출력 : 다시 원소 형태로 ['red', 'blue', 'red', 'green', 'blue', 'blue']

# counter객체는 연산 가능
par = ['leo', 'kiki', 'eden']
com = ['eden', 'kiki']

# 아래의 경우 출력 Counter({'leo': 1})
print(Counter(par) - Counter(com))

# 아래의 경우 출력 Counter()
print(Counter(com) - Counter(par))
```

</br>

* 반올림

```python
round(3.1415, 2)
# 결과 : 3.14

# 사사오입 주의. 반올림할 자리의 수가 5이면 반올림 할 때 앞자리의 숫자가 짝수면 내림하고 홀수면 올림 한다.
round(4.5)  #결과는 4
round(3.5)  #결과는 4

# 사사오입 막는 방법
def round_normal(n):
  if n - math.floor(n) < 0.5:
    return math.floor(n)
  return math.ceil(n)
```

</br>

* ASCII

```python
# char to ascii
ord('A')
# 65

# ascii to char
chr(65)
# A
```

</br>

* 2차원 배열

```python
# n by m array
dp = [[0]*m for i in range(n)]
```

</br>

* 문자열에서 숫자만 추출

```python
import re

s = 'dsfads123dsd12d 3 ds1'

# 결과 : ['123', '12', '3', '1']
print(re.findall('\d+', s))
```

</br>

* generator

```python
def square_numbers(nums):
    for i in nums:
        yield i * i

my_nums = square_numbers([1, 2, 3, 4, 5])

for num in my_nums:
    print num
```

generator는 모든 결과 값을 메모리에 저장하지 않기 때문에 더 좋은 퍼포먼스를 냄

</br>

* 이진수 변환

```python
# 이진수
num = 49

# 십진수 -> others
# 각 변환 값은 str 형태, 접두어 주의
bin(num)
# '0b101010'
oct(num)
hex(num)

# 접두어 없이 가능
format(42, 'b')
# '101010'
format(42, 'o')
# '52'
format(42, 'x')
# '2a'

# others -> 십진수
int('0b101010', 2)
int('0o52', 8)
int('0x2a', 16)
```

</br>

* comparator

```python
# [프로그래머스, 정렬, 가장 큰 수]
# cmp_to_key를 이용해 정렬 시, comparator 함수 반영 할 수 있음
from functools import cmp_to_key

def compare(a,b):
    n1 = a + b
    n2 = b + a
    return int(n2) - int(n1)

def solution(numbers):
    str_numbers = [str(x) for x in numbers]
    str_numbers.sort(key=cmp_to_key(compare))
    answer = str(int(''.join(str_numbers)))
    return answer
```

</br>

* 순열과 조합

```python
from itertools import permutations, combinations

chars = ['A', 'B', 'C']

# 두 번째 파라미터는 nP2, nC2에서 2를 의미
p = permutations(chars, 2)  # 순열
c = combinations(chars, 2)  # 조합

print(list(p))
print(list(c))
# 출력 결과
# [('A', 'B'), ('A', 'C'), ('B', 'A'), ('B', 'C'), ('C', 'A'), ('C', 'B')]
# [('A', 'B'), ('A', 'C'), ('B', 'C')]
```

</br>

* set

```python
# | : 합집합, c = a|b
# & : 교집합, c = a&b
# - : 차집합, c = a-b
# ^ : 대칭차집합 연산자(합집합 - 교집합), c = a^b
# 모두 = 연산자와 함께 사용될 수 있다. =, &=, -=, ^=

a = {1, 2, 3, 4, 5}
b = {3, 4, 5, 6, 7}
a |= b
# a
# {1, 2, 3, 4, 5, 6, 7}
```

</br>

* heap

https://www.daleseo.com/python-heapq/

`heapq` 모듈에은 파이썬의 보통 리스트를 마치 최소 힙처럼 다룰 수 있도록 도와준다.
자바의 `PriorityQueue` 클래스처럼 리스트와 별개의 자료구조가 아닌 점에 유의해야 한다. 그렇게 때문에, 그냥 빈 리스트를 생성해놓은 다음 `heapq` 모듈의 함수를 호출할 때 마다 이 리스트를 인자로 넘긴다. 다시말해, 파이썬에서는 `heapq` 모듈을 통해서 원소를 추가하거나 삭제한 **리스트**가 그냥 최소 힙이다.

```python
# 최소힙
import heapq

# 힙 생성
heap = []

# 원소 추가. O(logN)
heapq.heappush(heap, 4)
heapq.heappush(heap, 1)
heapq.heappush(heap, 7)
heapq.heappush(heap, 3)
print(heap)
# [1, 3, 7, 4]

# 원소 삭제. O(logN)
print(heapq.heappop(heap))
print(heap)
# 1
# [3, 4, 7]

# 삭제 안하고 값 얻기
print(heap[0])

# 기존 리스트 힙으로 변환
heap = [4, 1, 7, 3, 8, 5]
heapq.heapify(heap)
print(heap)
# [1, 3, 5, 4, 8, 7]

# 최대힙
import heapq

nums = [4, 1, 7, 3, 8, 5]
heap = []

for num in nums:
  heapq.heappush(heap, (-num, num)) # (우선 순위, 값)
  
# 힙에서 값을 읽어올 때는 각 튜플에서 인덱스 1에 있는 값을 취하면 된다.
print(heap)
# [(-8, 8), (-7, 7), (-5, 5), (-1, 1), (-3, 3), (-4, 4)]
```

</br>

* zip

```python
a = [1, 2, 3, 4]
b = [1, 2, 3]

for i, j in zip(a, b):
	print(i, j)

# 두 배열의 크기가 다르면 순서대로 나오되, 크기가 작은 배열까지만 출력. 에러 없음
# 1, 1
# 2, 2
# 3, 3
```

