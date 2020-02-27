## list



```python
>>> a = [1, 2, 3, 4, 5]
>>> a[0:2]
[1, 2]
```

* 한 listd에 여러 타입 상관 없다

```python
>>> a = [1, 2, 3, ['a', 'b', 'c'], 4, 5]
>>> a[2:5]
[3, ['a', 'b', 'c'], 4]
>>> a[3][:2]
['a', 'b']
```

* 배열 합치기

```python
>>> a = [1, 2, 3]
>>> b = [4, 5, 6]
>>> a + b
[1, 2, 3, 4, 5, 6]
```

* 배열 곱하기

```python
>>> a = [1, 2, 3]
>>> a * 3
[1, 2, 3, 1, 2, 3, 1, 2, 3]
```

* 리스트 수정할 때 주의할 점

2번 예제에서 리스트를 a[1:2] = ['a', 'b', 'c']로 수정하는 것과 a[1] = ['a', 'b', 'c']로 수정하는 것은 전혀 다른 결과값을 갖게 되므로 주의해야 한다. a[1] = ['a', 'b', 'c']는 리스트 a의 두 번째 요소를 ['a', 'b','c']로 바꾼다는 말이고 a[1:2]는 a[1]에서 a[2] 사이의 리스트를 ['a', 'b', 'c']로 바꾼다는 말이다. 따라서 a[1] = ['a', 'b', 'c']로 수정하게 되면 위와는 달리 리스트 a가 [1, ['a', 'b', 'c'], 4]라는 값으로 변하게 된다.

```python
>>> a = [1, 2, 3]
# 1번
>>> a[1:2] = ['a', 'b', 'c']
>>> a
[1, 'a', 'b', 'c', 4]

# 2번
>>> a[1] = ['a', 'b', 'c']
>>> a
[1, ['a', 'b', 'c'], 4]
```

* 삭제

```python
# 1번
>>> a[1:3] = [ ]
>>> a
[1, 'c', 4]
>>> a
[1, 'c', 4]
>>> del a[1]

# 2번
>>> a
[1, 4]

```

* 함수

```python
>>> a = [1, 2, 3]
>>> a.append(4)
>>> a
[1, 2, 3, 4]

>>> a.append([5,6])
>>> a
[1, 2, 3, 4, [5, 6]]

>>> a = [1, 4, 3, 2]
>>> a.sort()
>>> a
[1, 2, 3, 4]

>>> a = ['a', 'c', 'b']
>>> a.reverse()
>>> a
['b', 'c', 'a']

# 원소 3의 인덱스 찾기
>>> a = [1,2,3]
>>> a.index(3)
2
>>> a.index(1)
0

# 몇번 인덱스에 뭐 삽입
>>> a = [1, 2, 3]
>>> a.insert(0, 4)
[4, 1, 2, 3]

# 원소 3 지우기
>>> a = [1, 2, 3, 1, 2, 3]
>>> a.remove(3)
[1, 2, 1, 2, 3]

>>> a = [1,2,3]
>>> a.pop()
3
>>> a
[1, 2]

>>> a = [1,2,3]
>>> a.pop(1)
2
>>> a
[1, 3]

# 1몇 개인지
>>> a = [1,2,3,1]
>>> a.count(1)
2

# list의 size
>>> a = [1, 2, 3]
>>> len(a)
3

# extend(x)에서 x는 리스트만 위치할 수 있음
# a.extend([4,5])는 a += [4,5]와 동일
>>> a = [1,2,3]
>>> a.extend([4,5])
>>> a
[1, 2, 3, 4, 5]
>>> b = [6, 7]
>>> a.extend(b)
>>> a
[1, 2, 3, 4, 5, 6, 7]
```



* 삭제 방법 3가지

  a.remove(x) - x는 a리스트의 요소값
  a.pop(x) - x는 a리스트의 인덱스(del과의 차이점은 return값이 있다는 것)
  del a[x] - x는 a리스트의 인덱스



참고 자료

https://wikidocs.net/14 (점프 투 파이썬)