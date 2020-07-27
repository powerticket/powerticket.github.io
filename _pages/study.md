---
title: "Powerticket's Studying"
permalink: /study/
layout: single

---

[TOC]

***



# Studying

> Fast and steady win the race.
>



## Python

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



## Django



## C



