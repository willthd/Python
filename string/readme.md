* ## 문자열

  ```python
  print("=" * 50)
  print("My Program")
  print("=" * 50)
  ```

  - output

  ```
  ================================================== 
  My Program
  ==================================================
  ```

  

  ### slicing

  ```python
  a = "Life is too short, You need Python"
  print(a[3])
  print(a[-2])
  # 1부터 3전까지(0 <= a < 3)
  print(a[1:3])
  print(a[:6])
  b = a[0] + a[1] + a[2] + a[3]
  print(b)
  ```

  - output

  ```
  e
  o
  if
  Life i
  Life
  ```

  

  ### formatting

  ```python
  number = 10
  day = "three"
  print("I ate %d apples. so I was sick for %s days." % (number, day))
  ```

  - output

  ```
  I ate 10 apples. so I was sick for three days.
  ```

  

  | 코드 | 설명                      |
  | ---- | ------------------------- |
  | %s   | 문자열 (String)           |
  | %c   | 문자 1개(character)       |
  | %d   | 정수 (Integer)            |
  | %f   | 부동소수 (floating-point) |
  | %o   | 8진수                     |
  | %x   | 16진수                    |
  | %%   | Literal % (문자 `%` 자체) |

  여기서 재미있는 것은 %s 포맷 코드인데, 이 코드는 어떤 형태의 값이든 변환해 넣을 수 있다. 무슨 말인지 예를 통해 확인해 보자

  ```
  >>> "I have %s apples" % 3
  'I have 3 apples'
  >>> "rate is %s" % 3.234
  'rate is 3.234'
  ```

  3을 문자열 안에 삽입하려면 %d를 사용하고, 3.234를 삽입하려면 %f를 사용해야 한다. 하지만 %s를 사용하면 이런 것을 생각하지 않아도 된다. 왜냐하면 %s는 자동으로 % 뒤에 있는 값을 문자열로 바꾸기 때문이다

  

  **숫자 바로 대입하기**

  ```
  >>> "I eat {0} apples".format(3)
  'I eat 3 apples'
  ```

  **문자열 바로 대입하기**

  ```
  >>> "I eat {0} apples".format("five")
  'I eat five apples'
  ```

  

  참조 : https://wikidocs.net/13 (점프 투 파이썬)
