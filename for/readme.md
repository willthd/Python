## for

### for와 함께 자주 사용하는 range함수

```python
# range 객체 저장 가능
a = range(10)
print(a)

# 출력 결과 : range(0, 10)
# for i in a 가능

# range(시작, 끝, 증감)
for i in range(10, 7, -1):
	print(i)
	
# 출력 결과
# 10
# 9
# 8
```

</br>

### 리스트 안에 for문 포함하기

```python
result = [num * 3 for num in a]
print(result)
# [3, 6, 9, 12]
```

```python
result = [num * 3 for num in a if num % 2 == 0]
print(result)
# [6, 12]
```

```python
modified_numbers = [0 if number % 2 == 0 else 1 if number % 3 == 0 else number for number in numbers]
```

리스트 내포의 일반적인 문법은 다음과 같다. "if 조건" 부분은 앞의 예제에서 볼 수 있듯이 생략할 수 있다.

```python
[표현식 for 항목 in 반복가능객체 if 조건]
```

조금 복잡하지만 for문을 2개 이상 사용하는 것도 가능하다. for문을 여러 개 사용할 때의 문법은 다음과 같다.

```python
[표현식 for 항목1 in 반복가능객체1 if 조건1
        for 항목2 in 반복가능객체2 if 조건2
        ...
        for 항목n in 반복가능객체n if 조건n]
```

</br>

### for i in range(n)

```python
for i in range(5):
  if i == 2:
    i = 4
  print(i, end=' ')
  
# 출력 결과
# 0 1 4 3 4
# java와 다르게 for문 내에서 i 변경 불가능하다. 다만 최초 정의한대로 5회는 반복


# 반면에 while은 가능
i = 0
while i < 5:
    if i == 3:
        i = 5
    print(i, end=' ')
    i += 1

# 출력 결과
# 0 1 4
```

</br>

