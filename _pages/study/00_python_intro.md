# Python Basic

## Documents

[Python 3.7.8 documentation](https://docs.python.org/3.7/index.html)

[PEP 8 -- Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/)

[List of Unicode characters](https://en.wikipedia.org/wiki/List_of_Unicode_characters#Latin_script)

[점프 투 파이썬](https://wikidocs.net/book/1)



## Syntax

### Comment

- `#` at one line comment

  ```python
  # comment
  ```

- `'''` or `"""` at multi-line comments

  ```python
  '''
  multi
  line
  comments
  '''
  ```



### Code

- Statement is a minimum code which is executable. One statement at one line is a basic rule in making python code.

  ```python
  print('Hello, World!')
  ```

- Can use `;` when you want to code statements in one line.

  ```python
  print('Hello,'); print('World!')
  ```

* Can use `\` or `'''` when you want to code statements in multi-line.

  ```python
  print('Hello, \
  World!')
  ```

  ```python
  print('''Hello,
  World!''')
  ```

- Can code multi-line without `\` or `'''` when defines`()`, `{}`, `[]`

  ```python
  list_l = [
      'l1',
      'l2',
      'l3'
  ]
  ```

  

## Variable

### Assignment Operator: `=`

- In python, `=` means assignment, not equality.

  ```python
  x = 'value'
  ```

* Use `type()` when you want to identify the type of value.

  ```python
  type(x)
  ```

* Use `id()` when you want to identify the address of value.

  ```python
  id(x)
  ```

- Can assign same value at once

  ```python
  x = y = 'same value'
  print(x); print(y)
  ```

* Can assign different value at once

  ```python
  x, y = 'differnt', 'value'
  print(x); print(y)
  ```

- It is possible to swap each value.

  ```python
  x, y = 'differnt', 'value'
  print(x); print(y)
  x, y = y, x
  print(x); print(y)
  ```



### Identifier

Identifier is a name of variable, function, module or class.

* Identifier is composed of alphabet, underscore(`_`), digits.

* It is not allowed to use digit as a first letter.

* Length is unlimited.

* Upper and lower-case alphabet is distinguished.

* Reserved words below are not allowed to use as a identifier.

  ```python
  False, None, True, and, as, assert, break, class, continue, def, del, elif,
  else, except, finally, for, from, global, if, import, in, is, lambda, nonlocal,
  not, or, pass, raise, return, try, while, with, yield
  ```

- Can check reserved words by importing keyword.

  ```python
  import keyword
  print(keyword.kwlist)
  ```

* Have to avoid using a name of built-in function as a identifier.

  ```python
  print = 'hi'
  del print
  print(print)
  ```

  

## Data Type

- **Number**
- **String**
- **Boolean**

### Number
#### Integer

- No `long` type in python 3.x
- No overflow at `int` type unlike C language.
- Binary: `0b`, octal: `0o`, hexadecimal: `0x` number expressions

**파이썬에서 표현할 수 있는 가장 큰 수**

* 파이썬에서 가장 큰 숫자를 활용하기 위해 sys 모듈을 불러온다.
* 파이썬은 기존 C 계열 프로그래밍 언어와 다르게 정수 자료형(integer)에서 오버플로우가 없다.
* arbitrary-precision arithmetic를 사용하기 때문이다.

> **오버플로우(overflow)**
- 데이터 타입 별로 사용할 수 있는 메모리의 크기가 제한되어 있다.
- 표현할 수 있는 수의 범위를 넘어가는 연산을 하게 되면, 기대했던 값이 출력되지 않는 현상, 즉 메모리가 차고 넘쳐 흐르는 현상

> **arbitrary-precision arithmetic**
- [파이썬에서 아주 큰 정수를 표현할 때 사용하는 메모리의 크기 변화](https://mortada.net/can-integer-
operations-overflow-in-python.html)
- 사용할 수 있는 메모리양이 정해져 있는 기존의 방식과 달리, 현재 남아있는 만큼의 가용 메모리를 모두 수 표현에 끌어다 쓸 수 있는 형태
- 특정 값을 나타내는데 4바이트가 부족하다면 5바이트, 더 부족하면 6바이트까지 사용할 수 있게 유동적으로 운용

```python
# n진수를 만들어보고, 출력해봅시다.
binary_number = 0b10
print(binary_number)

octal_number = 0o10
print(octal_number)

hexadecimal_number = 0x10
print(hexadecimal_number)
```

```python
import sys
print(sys.maxsize * sys.maxsize)
```

### (2) `float` (부동소수점, 실수, floating point number)

실수는 `float`로 표현됩니다.

다만, 실수를 컴퓨터가 표현하는 과정에서 부동소수점을 사용하며, 항상 같은 값으로 일치되지 않습니다. (floating point
rounding error)

이는 컴퓨터가 2진수(비트)를 통해 숫자를 표현하는 과정에서 생기는 오류이며, 대부분의 경우는 중요하지 않으나 값을 같은지 비교하는 과정에서
문제가 발생할 수 있습니다.

```python
# 변수에 실수를 넣고 해당 변수의 type을 알아봅시다.
```

```python
b = 3.14
print(type(b))
```

#### 컴퓨터식 지수 표현 방식
* e를 사용할 수도 있다. (e와 E 둘 중 어느 것을 사용해도 무방)

```python
# 컴퓨터식 지수 표현 방식을 사용해봅시다.
```

```python
b = 314e-2
type(b)
```

#### 실수의 연산
* 실수의 경우 실제로 값을 처리하기 위해서는 조심할 필요가 있다.

```python
# 실수의 덧셈을 해봅시다.
```

```python
3.5 + 3.2
```

```python
# 실수의 뺄셈을 해봅시다.
```

```python
3.5 - 3.2
```

```python
# 우리가 원하는대로 반올림을 해봅시다.
# round() 는 0~4는 내림, 5는 동일하게 작동하지 않고 반올림 방식에 따라 다릅니다.
# 짝수에서 5는 내림 / 홀수에서 5는 올림
```

```python
round(3.5 - 3.2, 2)
```

```python
# 두 개의 값이 같은지 확인해봅시다.
```

```python
print(3.5 - 3.2)
print(0.3)
3.5 - 3.2 == 0.3
```

* 따라서 다음과 같은 방법으로 처리 할 수 있다. (이외에 다양한 방법이 있음)

```python
# 1. 기본적인 처리방법을 알아봅시다.
```

```python
a = 3.5 - 3.2
b = 0.3
round(a, 2) == b
```

```python
# 2. sys 모듈을 통해 처리하는 방법을 알아봅시다.
# `epsilon` 은 부동소수점 연산에서 반올림을 함으로써 발생하는 오차 상환
```

```python
import sys
print(sys.float_info.epsilon)

abs(a - b) <= sys.float_info.epsilon
```

```python
# 3. python 3.5부터 활용 가능한 math 모듈을 통해 처리하는 법을 알아봅시다.
```

```python
import math
math.isclose(a, b)
```

### (3) `complex` (복소수, complex number)

각각 실수로 표현되는 실수부와 허수부를 가집니다.

복소수는 허수부를 `j`로 표현합니다.

```python
# 변수에 복소수를 넣고 해당 변수의 type을 알아봅시다.
```

```python
a = 3 + 4j
type(a)
```

```python
# 문자열을 복소수로 변환해봅시다.
```

```python
b = complex('3+4j')
type(b)
```

```python
# 문자열을 변환할 때, 문자열은 중앙의 + 또는 - 연산자 주위에 공백을 포함해서는 안 됩니다.
```

```python
b = complex('3 + 4j')
type(b)
```

## 문자(String) 타입

### 기본 활용법

* 문자열은 Single quotes(`'`)나 Double quotes(`"`)을 활용하여 표현 가능하다.

    - 작은따옴표: `'"큰" 따옴표를 담을 수 있습니다'`

    - 큰따옴표: `"'작은' 따옴표를 담을 수 있습니다"`

    - 삼중 따옴표: `'''세 개의 작은따옴표'''`, `"""세 개의 큰따옴표"""`


* 단, 문자열을 묶을 때 동일한 문장부호를 활용해야하며, `PEP-8`에서는 **하나의 문장부호를 선택**하여 유지하도록 하고 있다.
(Pick a rule and Stick to it)

```python
# 변수에 문자열을 넣고 출력해봅시다.
```

```python
greeting = 'hello'
type(greeting)
```

```python
# 사용자에게 받은 입력은 기본적으로 str입니다.
```

```python
number = input('숫자를 입력해주세요 : ')
print(number * 2)
number = input('숫자를 입력해주세요 : ')
print(int(number) * 2)
```

#### 따옴표 사용

문자열 안에 문장부호(`'`, `"`)가 사용될 경우 이스케이프 문자(`\`)를 활용 가능 합니다.

```python
# 문자열 안에 문장부호를 활용해서 오류를 확인해봅시다.
```

```python
print("he's cool")
print("그의 이름은 "ssafy"였다")
```

```python
# 오류를 이스케이프 문자와 서로 다른 문장부호를 통해 해결해봅시다.
```

```python
print("he's cool")
print("그의 이름은 \"ssafy\"였다")
```

여러줄에 걸쳐있는 문장은 다음과 같이 표현 가능합니다.

* `PEP-8`에 따르면 이 경우에는 반드시 `"""`를 사용하도록 되어 있다.

```python
# 여러줄을 출력해봅시다.
```

```python
print("""
이건
여러 줄에 걸친
문자열입니다.
""")
```

```python
# 문자열은 + 연산자로 이어붙이고, * 연산자로 반복시킬 수 있습니다.
```

```python
# Concatenation -> 문자열 합치기
print('Hello ' + 'ssafy')
# Interpolation -> 문자열 반복
print('Hello ' * 3)
```

```python
# 변수화해서도 사용가능합니다.
```

```python
name = 'john'

'my name is ' * 2 + name * 2
```

```python
# 두 개 이상의 문자열이 연속해서 나타나면 자동으로 이어 붙여집니다.
```

```python
'hello' 'ssafy'
```

### 이스케이프 시퀀스

문자열을 활용하는 경우 특수문자 혹은 조작을 하기 위하여 사용되는 것으로 `\`를 활용하여 이를 구분합니다.

|<center>예약문자</center>|내용(의미)|
|:--------:|:--------:|
|\n|줄 바꿈|
|\t|탭|
|\r|캐리지리턴|
|\0|널(Null)|
|\\\\ |`\`|
|\\'|단일인용부호(`'`)|
|\\"|이중인용부호(`"`)|

```python
# 이스케이프 문자열을 조합하여 프린트해봅시다.
```

```python
print('''안녕
나는
python이야\n''')
print('안녕\n나는\npython\t이야')
```

```python
# print를 하는 과정에서도 이스케이프 문자열을 활용 가능합니다.
```

```python
print('\\ - $ 환율')
print('\ - $ 환율')
print("이건 \"python\"입니다.")
```

```python
# 물론, end 옵션은 이스케이프 문자열이 아닌 다른 것도 가능합니다.
```

```python
print('hello', end = ",\t2020")
print('ssafy')
```

### String interpolation

* `%-formatting`

* [`str.format()` ](https://pyformat.info/)

* [`f-strings`](https://www.python.org/dev/peps/pep-0498/) : 파이썬 3.6 이후 버전에서 지원

```python
# name 변수에 이름을 입력해봅시다.
```

```python
name = 'ashley'
```

```python
# %-formatting을 활용해봅시다.
```

```python
print('내 이름은 %s입니다.' % name)
```

```python
# str.format()을 활용해봅시다.
```

```python
print('내 이름은 {}입니다.'.format(name))
```

```python
# f-string을 활용해봅시다.
```

```python
print(f"내 이름은 {name}입니다.")
```

```python
# 여러줄 문자열에서도 사용 가능합니다.
```

```python
print(f'''내 이름은
{name}
입니다.''')
```

* f-strings에서는 형식을 지정할 수 있다.

```python
# 다양한 형식을 활용하기 위해 datetime 모듈로 오늘을 표현해봅시다.
```

```python
import datetime
now = datetime.datetime.now()
print(now)
```

```python
# interpolation에서 출력형식을 지정할 수 있습니다.
```

```python
print(f'올해는 {now:%Y}년, 이번 달은 {now:%m}월, 오늘은 {now:%d}일')
```

* f-strings에서는 연산과 출력형식 지정도 가능하다.

```python
# string interpolation을 통해 출력형식 지정 뿐만 아니라, 연산도 가능합니다.
```

```python
pi = 3.141592
r = 10
print(f'{pi:.3}, 넓이는 {pi * r * r:.3}')
```

## 참/거짓(Boolean) 타입

파이썬에는 `True`와 `False`로 이뤄진 `bool` 타입이 있습니다.

비교/논리 연산을 수행 등에서 활용됩니다.

다음은 `False`로 변환됩니다.
```
0, 0.0, (), [], {}, '', None
```

```python
# True와 False의 타입들을 알아봅시다.
```

```python
type(True)
type(False)
```

```python
# 다양한 True, False 상황들을 확인해봅시다.
# 형변환(Type Conversion)에서 추가적으로 다루는 내용입니다.
```

```python
print(bool(0))
print(bool(.0))
print(bool(0.))
print(bool(0.00000000))
print(bool(False))
print(bool(()))
print(bool([]))
print(bool({}))
print(bool(''))
print(bool(""))
print(bool(None))
```

### `None` 타입

파이썬에서는 값이 없음을 표현하기 위해 `None` 타입이 존재합니다.

```python
# None의 타입을 알아봅시다.
```

```python
type(None)
```

```python
# 변수에 저장해서 확인해봅시다.
```

```python
a = None
print(type(a))
print(a)
type(a)
```

## 형변환(Type conversion, Typecasting)

파이썬에서 데이터타입은 서로 변환할 수 있습니다.

- 암시적 형변환
- 명시적 형변환

### 암시적 형변환(Implicit Type Conversion)

사용자가 의도하지 않았지만, 파이썬 내부적으로 자동으로 형변환 하는 경우입니다.
아래의 상황에서만 가능합니다.
* bool
* Numbers (int, float, complex)

```python
# boolean과 integer는 더할 수 있을까요?
```

```python
print(True + 3)
print(False + 3)
int(True)
```

```python
result = None
result + 3
```

```python
check_passed = False
check_passed + 3
```

```python
# int, float, complex를 각각 변수에 대입해봅시다.
```

```python
int_number = 2020
float_number = 3.14
complex_number = 2 + 3j
```

```python
# int와 float를 더해봅시다. 그 결과의 type은 무엇일까요?
```

```python
print(int_number + float_number)
print(type(int_number + float_number))
```

```python
# int와 complex를 더해봅시다. 그 결과의 type은 무엇일까요?
```

```python
print(int_number + complex_number)
print(type(int_number + complex_number))
```

### 명시적 형변환(Explicit Type Conversion)
위의 상황을 제외하고는 모두 명시적으로 형 변환을 해주어야합니다.

* string -> intger  : 형식에 맞는 숫자만 가능
* integer -> string : 모두 가능

암시적 형변환이 되는 모든 경우도 명시적으로 형변환이 가능합니다.

* `int()` : string, float를 int로 변환
* `float()` : string, int를 float로 변환
* `str()` : int, float, list, tuple, dictionary를 문자열로 변환

`list()`, `tuple()` 등은 다음 챕터에서 배울 예정입니다.

```python
# integer와 string 사이의 관계는 명시적으로 형변환을 해줘야만 합니다.
```

```python
1 + '등'
```

```python
# string 3을 integer로 변환해봅시다.
```

```python
print('1' + '등')
print(str(1) + '등')
```

```python
# string 3.5를 float로 변환해봅시다.
```

```python
type(float(3.5))
```

```python
# string은 글자가 숫자일때만 형변환이 가능합니다.
```

```python
float(3,5)
```

```python
# string 3.5를 int로 변환할 수는 없습니다.
```

```python
int('3.5')
```

```python
# float 3.5는 int로 변환이 가능합니다.
```

```python
int(float('3.5'))
```

# 연산자(Operator)

- 산술 연산자
- 비교 연산자
- 논리 연산자
- 복합 연산자
- 기타 연산자

## 산술 연산자
Python에서는 기본적인 사칙연산이 가능합니다.

|연산자|내용|
|----|---|
|+|덧셈|
|-|뺄셈|
|\*|곱셈|
|/|나눗셈|
|//|몫|
|%|나머지(modulo)|
|\*\*|거듭제곱|

- 나눗셈 (`/`) 은 항상 float를 돌려준다.
- 정수 나눗셈 으로 (소수부 없이) 정수 결과를 얻으려면 `//` 연산자를 사용한다.

```python
# 2의 1000승을 확인해봅시다.
```

```python
2 ** 1000
```

```python
# 나눗셈과 관련된 산술연산자를 활용해봅시다.
```

```python
print(type(5 / 2))
print(5 / 2)
print(type(5 // 2))
print(5 // 2)
print(type(5 % 2))
print(5 % 2)
```

```python
# divmod는 나눗셈과 관련된 함수입니다.
```

```python
divmod(5, 2)
```

```python
# 음수 양수 표현도 해봅시다.
```

```python
num = 2020
-num
```

## 비교 연산자

우리가 수학에서 배운 연산자와 동일하게 값을 비교할 수 있습니다.

|연산자|내용|
|----|---|
|`<`|미만|
|`<=`|이하|
|`>`|초과|
|`>=`|이상|
|`==`|같음|
|`!=`|같지않음|
|`is`|객체 아이덴티티|
|`is not`|부정된 객체 아이덴티티|

```python
# 숫자의 대소관계를 비교해봅시다.
```

```python
print(5 >= 1)
print(3 > 6)
```

```python
# 다른 숫자인지 확인해봅시다.
```

```python
3 != 3.0
```

```python
# 같은 숫자인지 확인해봅시다.
```

```python
3.0000000000000000000000000 == 3.0
```

```python
# 문자열도 같은지 확인해봅시다.
```

```python
print('hello' == 'hello')
print('hello' == 'Hello')
```

## 논리 연산자

|연산자|내용|
|---|---|
|a and b|a와 b 모두 True시만 True|
|a or b|a 와 b 모두 False시만 False|
|not a|True -> False, False -> True|

우리가 보통 알고 있는 `&` `|`은 파이썬에서 비트 연산자입니다.

```python
# and과 관련해서 모든 case를 출력해봅시다.
```

```python
print(True and True)
print(True and False)
print(False and True)
print(False and False)
```

```python
# or과 관련해서 모든 case를 출력해봅시다.
```

```python
print(True or True)
print(True or False)
print(False or True)
print(False or False)
```

```python
# not을 활용해봅시다.
```

```python
print(not True)
print(not False)
```

* 파이썬에서 and는 a가 거짓이면 a를 리턴하고, 참이면 b를 리턴한다.
* 파이썬에서 or은 a가 참이면 a를 리턴하고, 거짓이면 b를 리턴한다.

### 단축평가
* 첫 번째 값이 확실할 때, 두 번째 값은 확인 하지 않음
* 조건문에서 뒷 부분을 판단하지 않아도 되기 때문에 속도 향상

```python
vowels = ['a', 'e', 'i', 'o', 'u']
```

```python
print('b' and 'a' in vowels)
print('a' and 'b' in vowels)
print('b' or 'a' in vowels)
print('a' or 'b' in vowels)
```

```python
print('a' and 'b') # 파이썬에서 and는 a가 거짓이면 a를 리턴하고, 참이면 b를 리턴한다.
print('a' or 'b')  # 파이썬에서 or은 a가 참이면 a를 리턴하고, 거짓이면 b를 리턴한다.
print(False and 'b')
print(False or 'b')
```

```python

```

```python

```

- `and` 는 둘 다 True일 경우만 True이기 때문에 첫번째 값이 True라도 두번째 값을 확인해야 하기 때문에 'b'가 반환된다.
- `or` 는 하나만 True라도 True이기 때문에 True를 만나면 해당 값을 바로 반환한다.

```python
# and의 단축평가(short-circuit evaluation)에 대해서 알아봅시다.
```

```python

```

```python
# or의 단축평가(short-circuit evaluation)에 대해서 알아봅시다.
```

```python

```

## 복합 연산자

복합 연산자는 연산과 대입이 함께 이뤄집니다.

가장 많이 활용되는 경우는 반복문을 통해서 개수를 카운트하거나 할 때 활용됩니다.

|연산자|내용|
|----|---|
|a += b|a = a + b|
|a -= b|a = a - b|
|a \*= b|a = a \* b|
|a /= b|a = a / b|
|a //= b|a = a // b|
|a %= b|a = a % b|
|a \*\*= b|a = a ** b|

```python
# 복합연산자는 이럴 때 사용됩니다.
```

```python
cnt = 0
while cnt < 5:
  print(cnt)
  cnt = cnt + 1
print()
cnt = 0
while cnt < 5:
  print(cnt)
  cnt += 1
```

## 기타 주요 연산자

### Concatenation

숫자가 아닌 자료형은 `+` 연산자를 통해 합칠 수 있습니다.

```python
# 문자열을 더해봅시다.(합쳐봅시다.)
```

```python
'pp' + 'ap'
```

```python
# list를 더해봅시다.(합쳐봅시다.)
```

```python
[1, 2, 3] + [4, 5, 6] + [1, 2, 3]
```

### Containment Test

`in` 연산자를 통해 요소가 속해있는지 여부를 확인할 수 있습니다.

```python
# 문자열안에 특정한 문자가 있는지 확인해봅시다.
```

```python
print('a' in 'hello')
print('e' in 'hello')
```

```python
# list안에 특정한 원소가 있는지 확인해봅시다.
```

```python
print(0 in [1, 2, 3, 5, 7])
print(5 in [1, 2, 3, 5, 7])
```

```python
# range안에 특정한 원소가 있는지 확인해봅시다.
```

```python
print(45 in range(45))
print(45 in range(46))
```

### Identity

`is` 연산자를 통해 동일한 object인지 확인할 수 있습니다. (OOP 파트에서 다시 학습하게 됩니다.)

```python
# 파이썬에서 -5 부터 256 까지의 id는 동일합니다.
```

```python
print(id(5))
print(id(6))
print(id(7))
```

```python
# 257 이루의 id 는 다릅니다.
```

```python
a = [1, 2, 3]
b = [1, 2, 3]
print(a == b)
print(id(a))
print(id(b))
print(a is b) # print(id(a) == id(b))
```

### Indexing/Slicing
`[]`를 통한 값을 접근하고, `[:]`을 통해 리스트를 슬라이싱할 수 있습니다. (Container 파트에서 자세하게 학습합니다.)

```python
# 문자열을 인덱싱을 통해 값에 접근해봅시다.
```

```python
print([1, 2, 3, 4, 5][3])
print([1, 2, 3, 4, 5][1:3])
print([1, 2, 3, 4, 5][1:3][0:])
print([1, 2, 3, 4, 5][1:3][0:][0])
```

## 연산자 우선순위

0. `()`을 통한 grouping

1. Slicing

2. Indexing

3. 제곱연산자
    `**`

4. 단항연산자
    `+`, `-` (음수/양수 부호)

5. 산술연산자
    `*`, `/`, `%`

6. 산술연산자
    `+`, `-`

7. 비교연산자, `in`, `is`

8. `not`

9. `and`

10. `or`

```python
# 우선순위를 확인해봅시다.
```

```python
print(-3 ** 6)
print((-3) ** 6)
```

### [참고] 표현식(Expression) & 문장(Statement)

### 표현식(Expression)

> 표현식 => `evaluate` => 값

* 하나의 값(value)으로 환원(reduce)될 수 있는 문장
* `식별자`, `값`(리터럴), `연산자`로 구성됩니다.
* 표현식을 만드는 문법(syntax)은 일반적인 (중위표기) 수식의 규칙과 유사합니다.
* [참고] [표현식(Expression) 문법 관련
공식문서](https://docs.python.org/3/reference/expressions.html)

```python
# 하나의 값(value)도 표현식(expression)이 될 수 있습니다.
```

```python
35 + 35
```

```python
# 표현식은 하나의 값으로 평가(evaluate)될 수 있어야 합니다. 그러면 할당문(assignment statement)은 표현식일까요?
```

```python
a = 5 # 할당문은 표현식이 아니다.
a
```

```python
# 식별자가 값이 할당되어 있는 경우 수식의 일부가 될 수 있습니다.
```

```python
3 + a
```

```python
# 표현식을 만드는 문법(syntax)은 일반적인 (중위표기) 수식의 규칙과 유사합니다. 아래와 같은 문장은 표현식이 될 수 없습니다.
```

```python
3 ** 4 + 4 ** 2
```

### 문장(Statement)

* 파이썬이 실행 가능한 최소한의 코드 단위 (a syntatic unit of programming)

```python
# 하나의 값(value)도 문장이 될 수 있습니다.
```

```python
'hello'
```

```python
# 표현식(expression)도 문장이 될 수 있습니다.
```

```python
3 + 5
```

```python
# 실행 가능(executable)해야 하기 때문에 아래의 코드는 문장이 될 수 없습니다.
```

```python
print(
```

### 문장과 표현식의 관계

<center><img width="600" height="300" src="https://user-
images.githubusercontent.com/9452521/87619771-f41f5e00-c757-11ea-9e4b-1f76e4ca0981.png",
alt="variable"/></center>

# 정리

## 변수(Variable)와 자료형(Data Type)

<center><img width=800 height=400 src="https://user-
images.githubusercontent.com/9452521/87640197-55a7f280-c781-11ea-9cff-19c022ce704a.png",
alt="variable"/></center>
