---
title: Python에서 "ValueError-invalid literal for int() with base 10" 오류 해결 방법
date: 2023-08-28 20:00:00 +0900
categories:
  - python
tags:
  - Python에러
  - ValueError
---
## 오류 발생 상황

Python에서 숫자와 문자열을 처리할 때 가끔 `"ValueError: invalid literal for int() with base 10"`라는 오류 메시지가 나타납니다. 이 메시지는 `int()` 함수를 사용하여 문자열을 정수로 변환하려고 할 때 발생하는 것이 일반적입니다.

## 원인 분석

이 오류가 발생하는 주된 이유는 `int()` 함수에 전달된 문자열이 숫자로 바꿀 수 없는 형식이기 때문입니다. 예를 들어, 숫자와 문자가 섞인 문자열이거나 공백이 포함된 경우입니다.

```python
# 잘못된 예시
int("123a")  # 숫자와 문자가 섞여 있음
int(" 123 ")  # 공백이 포함되어 있음
```

## 해결 방안

### 문자열 정제하기

문자열을 정수로 변환하기 전에, 그 문자열이 실제로 숫자만을 포함하고 있는지 확인하는 것이 중요합니다. `strip()` 함수를 사용하여 양쪽의 공백을 제거할 수 있습니다.

```python
# 예시
num_str = " 123 "
clean_str = num_str.strip()  # "123"
```

### 예외 처리 사용하기

`try-except` 구문을 사용하여 예외를 처리할 수 있습니다. 이 방법을 사용하면, 오류가 발생하더라도 프로그램이 중단되지 않습니다.

```python
# 예시
try:
    num = int("123a")
except ValueError:
    print("숫자로 변환할 수 없습니다.")
```

### isdigit 메서드 사용하기

문자열이 숫자만으로 이루어져 있는지 확인하는 또 다른 방법은 `isdigit()` 메서드를 사용하는 것입니다. 

```python
# 예시
if "123".isdigit():
    num = int("123")
```

## 정리

Python에서 `ValueError: invalid literal for int() with base 10` 오류는 주로 문자열을 정수로 변환하려 할 때 발생합니다. 이 문제를 해결하기 위해 문자열을 먼저 정제하거나, 예외 처리를 사용하거나, 문자열이 숫자만을 포함하는지 확인해야 합니다. 이러한 방법들을 적절히 조합하여 사용하면 대부분의 문제를 해결할 수 있습니다.