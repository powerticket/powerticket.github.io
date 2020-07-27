# 컨테이너(Container)
여러 개의 값을 저장할 수 있는 것(~~객체~~)

- 시퀀스(Sequence)형: 순서가 있는(ordered) 데이터
- 비 시퀀스(Non-sequence)형: 순서가 없는(unordered) 데이터

## 시퀀스(sequence)형 컨테이너

`시퀀스`는 데이터가 순서대로 나열된(ordered) 형식을 나타냅니다.

* **주의! 순서대로 나열된 것이 `정렬되었다(sorted)`라는 뜻은 아니다.**

### 특징
1. 순서를 가질 수 있다.

2. **특정 위치의 데이터를 가리킬 수 있다.**

### 종류
파이썬에서 기본적인 시퀀스 타입은 다음과 같습니다.

* 리스트(list)

* 튜플(tuple)

* 레인지(range)

* *문자형(string)*

* *바이너리(binary)* : 따로 다루지는 않습니다.


## 리스트(`list`)

<center><img src="https://user-
images.githubusercontent.com/18046097/61180421-fe90ae80-a650-11e9-8211-d06f87756d05.png",
alt="list figure"/></center>

**활용법**
```python
[value1, value2, value3]
```

리스트는 대괄호`[]` 및 `list()` 를 통해 만들 수 있습니다.

값에 대한 접근은 `list[i]`를 통해 합니다.

```python
# 빈 리스트를 만들어봅시다.
```

```python
l = []
ll = list()
print(type(l))
print(type(ll))
```

```python
# 원소를 포함한 리스트를 만들어봅시다.
```

```python
numbers = [1, 3, 5, 7, 9]
print(type(numbers))
print(numbers)
```

```python
# 첫번째 값에 접근해봅시다.
```

```python
numbers[2:4]
```

## 튜플(`tuple`)

**활용법**
```python
(value1, value2)
```

튜플은 리스트와 유사하지만, `()`로 묶어서 표현합니다.

그리고 tuple은 수정 불가능(불변, immutable)하고, 읽을 수 밖에 없습니다.

직접 사용하기 보다는 파이썬 내부에서 다양한 용도로 활용되고 있습니다.

```python
# tuple을 만들어봅시다.
```

```python
nums = (1, 2)
print(nums)
print(type(nums))
```

```python
# 아래와 같이 만들 수 있습니다.
```

```python
nums = 1, 2
print(nums)
print(type(nums))
```

```python
# 파이썬 내부에서는 다음과 같이 활용됩니다.
# 앞선 2. 변수 및 자료형 예제에서 사용된 코드입니다.
```

```python
x, y = 1, 2
print(x)
print(y)
print(x, y)
```

```python
# 실제로는 tuple로 처리됩니다.
```

```python
x, y = 1, 2
print(x)
print(y)
print(x, y)
```

```python
# 변수의 값을 swap하는 코드 역시 tuple을 활용하고 있습니다. 
```

```python
x, y = y, x
print(x, y)
```

```python
# 빈 튜플은 빈 괄호 쌍으로 만들어집니다.
```

```python
nums = ()
print(nums)
print(type(nums))
```

```python
# 하나의 항목으로 구성된 튜플은 값 뒤에 쉼표를 붙여서 만듭니다.
```

```python
nums = (1, )
print(nums)
print(type(nums))
```

```python
# Tuple 객체는 수정할 수 없습니다.

```

```python
nums = (1, 2, 3)
nums[0] = 4
```

## 레인지(`range()`)

`range` 는 숫자의 시퀀스를 나타내기 위해 사용됩니다.

기본형 : `range(n)`


> 0부터 n-1까지 값을 가짐


범위 지정 : `range(n, m)`

> n부터 m-1까지 값을 가짐

범위 및 스텝 지정 : `range(n, m, s)`

> n부터 m-1까지 +s만큼 증가한다

```python
# range를 만들어봅시다.
```

```python
nums = range(3)
print(nums)
print(type(nums))
```

```python
# range에 담긴 값을 list로 바꿔서 확인해봅시다.
```

```python
list(nums)
```

```python
# 4 ~ 8까지의 숫자를 담은 range를 만들어봅시다.
```

```python
range(4, 9)
```

```python
range(4, 8)
```

```python
# 0부터 -9까지 담긴 range를 만들어봅시다.
```

```python
print(list(range(0, -10, -1)))
print(list(range(-9, 1)))
```

```python
# 0부터 20까지 짝수만 가지는 range
list(range(2, 21, 2))
```


## 시퀀스에서 활용할 수 있는 연산자/함수

|operation|설명|
|---------|---|
|x `in` s	|containment test|
|x `not in` s|containment test|
|s1 `+` s2|concatenation|
|s `*` n|n번만큼 반복하여 더하기
|`s[i]`|indexing|
|`s[i:j]`|slicing|
|`s[i:j:k`]|k간격으로 slicing|
|len(s)|길이|
|min(s)|최솟값|
|max(s)|최댓값|
|s.count(x)|x의 개수|

```python
# containment test를 확인해봅시다.
```

```python
cart = ['apple', 'banana']
'banana' not in cart
```

```python
# concatenation(연결, 연쇄)를 해봅시다.
```

```python
[1, 2] + [3, 4]
```

```python
# 숫자 0이 6개 있는 list를 만들어봅시다.
```

```python
[0] * 6
```

```python
# indexing과 slicing을 하기 위해 list하나를 만들어주세요.
```

```python
location = ['서울', '대전', '광주', '구미']
location[1]
```

```python
# 두번째, 세번째 값만 가져와봅시다.
```

```python
location[1:3]
```

```python
# 0부터 30까지의 숫자를 3씩 증가시킨 리스트로 만들어봅시다.

```

```python
nums = range(0, 31)
print(list(nums)[0:len(nums):3])
print(list(nums)[0::3])
print(list(nums)[::3])
```

```python
# 위에서 만든 list의 길이를 확인해봅시다.
```

```python

```

```python
# 위에서 만든 list의 최솟값, 최댓값을 확인해봅시다.
```

```python

```

```python
# list에 담긴 특정한 것의 개수를 확인할 수도 있습니다.
```

```python

```

# 비 시퀀스형(Non-sequence) 컨테이너

- 셋(set)

- 딕셔너리(dictionary)

## `set`

`set`은 순서가 없는 자료구조입니다.

* `set`은 수학에서의 집합과 동일하게 처리된다.

* `set`은 중괄호`{}`를 통해 만들며, 순서가 없고 중복된 값이 없다.

* 빈 집합을 만들려면 `set()`을 사용해야 합니다. (`{}`로 사용 불가능.)

### 활용법
```python
{value1, value2, value3}
```

```python
# set 두개를 만들어서 연산자들을 활용해봅시다.
```

```python
a = {1, 2, 3}
print(a)
print(type(a))
```

```python
# set은 중복된 값이 있을 수 없습니다.
```

```python
a = {1, 1, 2, 3}
print(a)
```

* `set`을 활용하면 `list`의 중복된 값을 손쉽게 제거할 수 있습니다.

```python
# set으로 중복된 값을 제거해봅시다.
```

```python
nums = [3, 3, 1, 1, 2, 2]
print(nums)
set_nums = set(nums)
print(set_nums)
```

```python
# 다시 list로 바꿔서 확인해봅시다.
```

```python
nums = list(set_nums)
print(nums)
```

## `dictionary`

`dictionary`는 `key`와 `value`가 쌍으로 이뤄져있으며, 궁극의 자료구조이다.


<center><img src="https://user-
images.githubusercontent.com/18046097/61180427-1405d880-a651-11e9-94e1-1cc5c2a2ff34.png"></center>

### 활용법

```python
{Key1:Value1, Key2:Value2, Key3:Value3, ...}
```

* `{}`를 통해 만들며, `dict()`로 만들 수도 있다.
* `key`는 **변경 불가능(immutable)한 데이터**만 가능하다. (immutable : string, integer, float,
boolean, tuple, range)
* `value`는 `list`, `dictionary`를 포함한 모든 것이 가능하다.

```python
# 비어있는 dictionary를 두가지 방법으로 만들어봅시다.
```

```python

```

```python
# dictionary는 중복된 key는 존재할 수가 없습니다.
```

```python

```

```python
# 지역번호(서울-02 경기-031)가 담긴 전화번호부를 만들어봅시다.
```

```python

```

```python
# 딕셔너리의 .keys() 메소드를 활용하여 key를 확인 해볼 수 있습니다.
```

```python
cart = {
    'a': 'apple',
    'b': 'banana',
    'c': 'carrot'
}
cart.keys()
```

```python
# 딕셔너리의 .values() 메소드를 활용하여 value를 확인 해볼 수 있습니다.
```

```python
cart.values()
```

```python
# 딕셔너리의 .items() 메소드를 활용하여 key, value를 확인 해볼 수 있습니다.
```

```python
cart.items()

# for item in cart.items():
#   key, value = item
#   print(key, value)

for key, value in cart.items():
  print(key, value)
```

## 컨테이너형 형변환

파이썬에서 컨테이너는 서로 변환할 수 있습니다.

<img width="708" alt="typecasting" src="https://user-
images.githubusercontent.com/18046097/61180466-a6a67780-a651-11e9-8c0a-adb9e1ee04de.png">

```python
# list를 형 변환 해봅시다
```

```python

```

```python
# tuple을 형 변환 해봅시다
```

```python

```

```python
# range를 형 변환 해봅시다
```

```python

```

```python
# set을 형 변환 해봅시다
```

```python

```

```python
# dictionary를 형 변환 해봅시다
```

```python

```

## 데이터의 분류 (*중요*!)
> `mutable` vs. `immutable`

데이터는 크게 변경 가능한 것(`mutable`)들과 변경 불가능한 것(`immutable`)으로 나뉘며, python은 각각을 다르게
다룹니다.

### 변경 불가능한(`immutable`) 데이터

단일 데이터들

- **숫자(Number)**
- **글자(String)**
- **참/거짓(Bool)**

그리고

```python
range(), tuple(), frozenset()
```

```python
# immutable 데이터의 복사는 어떻게 이루어질까?
num1 = 20
num2 = num1 
num2 = 10

print(a)
print(b)
```

```python
%%html
<iframe width="800" height="500" frameborder="0" src="http://pythontutor.com/iframe-embed.html#code=a%20%3D%2020%0Ab%20%3D%20a%0Ab%20%3D%2010%0A%0Aprint%28a%29%0Aprint%28b%29&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=0&heapPrimitives=nevernest&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>
```

### 변경 가능한(`mutable`) 데이터

컨테이너 (~~`tuple`, `range()`, `frozenset`~~)

- `list`
- `dict`
- `set`
- 사용자가 만든 데이터 타입

```python
# mutable 데이터의 복사는 어떻게 이루어질까?
num1 = [1, 2, 3, 4]
num2 = num1
num2[0] = 100

print(num1)
print(num2)
```

```python
%%html
<iframe width="800" height="500" frameborder="0" src="http://pythontutor.com/iframe-embed.html#code=num1%20%3D%20%5B1,%202,%203,%204%5D%0Anum2%20%3D%20num1%0Anum2%5B0%5D%20%3D%20100%0A%0Aprint%28num1%29%0Aprint%28num2%29&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=0&heapPrimitives=nevernest&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>
```

# 정리
## 컨테이너(Container)
<center><img src="https://user-
images.githubusercontent.com/18046097/61180439-44e60d80-a651-11e9-9adc-e60fa57c2165.png",
alt="container"/></center>
