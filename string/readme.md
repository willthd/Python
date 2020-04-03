## 문자열

### slicing

```python
a = "Life is too short, You need Python"
print(a[3])
# e
print(a[-2])
# o
print(a[1:3])
# if
print(a[:6])
# Life i
```

</br>

### formatting

```python
number = 10
day = "three"
print("I ate %d apples. so I was sick for %s days." % (number, day))

# 출력
# I ate 10 apples. so I was sick for three days.
```

</br>

### 기타

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

### string에서 ==와 is의 차이

```python
a = "pub"
b = ''.join(["p", "u", "b"])

# a == b일 경우 True. 값을 비교
# a is b일 경우 False. 객체 자체를 비교
```

