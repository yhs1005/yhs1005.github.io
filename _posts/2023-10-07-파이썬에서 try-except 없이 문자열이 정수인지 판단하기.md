---
title: 파이썬에서 try-except 없이 문자열이 정수인지 판단하기
date: 2023-10-07 20:00:00 +0900
categories:
  - python
tags:
  - Python
  - 문자열확인
  - try-except
---
## 개요

파이썬에서 문자열이 정수형인지 아닌지를 판단하는 방법은 여러 가지가 있습니다. 그중에서도 `try-except` 구문을 사용하는 방법이 일반적이지만, 이번에는 `try-except` 없이 이를 판단하는 다른 방법들을 소개하겠습니다.

## `str.isdigit` 메서드 사용하기

첫 번째로 고려할 수 있는 방법은 문자열의 `isdigit` 메서드를 사용하는 것입니다. 이 메서드는 문자열이 모두 숫자로만 이루어져 있는지 확인합니다.

```python
def is_int(s):
    return s.isdigit()

print(is_int("123"))  # True
print(is_int("abc"))  # False
```

하지만 이 방법은 음수나 소수점을 포함한 숫자에는 적용되지 않습니다.

## `str.lstrip`과 조합하기

음수를 처리하려면 `lstrip` 메서드를 사용하여 음수 기호를 제거한 뒤 `isdigit` 메서드를 적용할 수 있습니다.

```python
def is_int(s):
    return s.lstrip('-').isdigit()

print(is_int("-123"))  # True
```

## 정규표현식 사용하기

또다른 방법은 정규표현식(regular expression)을 사용하는 것입니다. 정규표현식은 문자열의 패턴을 검사하는 데 사용됩니다. `re` 라이브러리의 `fullmatch` 함수를 사용할 수 있습니다.

```python
import re

def is_int(s):
    return bool(re.fullmatch(r'-?\d+', s))

print(is_int("123"))  # True
print(is_int("-123"))  # True
print(is_int("abc"))  # False
```

이 방법은 음수와 양수 모두를 처리할 수 있으며, 상대적으로 유연합니다.

## 결론

`try-except`를 사용하지 않고 파이썬에서 문자열이 정수인지 판단하는 방법은 여러 가지가 있습니다. `isdigit` 메서드는 간단한 경우에 유용하며, `lstrip`과 조합하거나 정규표현식을 사용하면 더 복잡한 경우에도 대응할 수 있습니다. 이러한 방법들은 각각의 상황에 따라 적절히 활용할 수 있습니다.