---
title: Python Requests 모듈에서 try-except 사용하기
date: 2023-08-25 20:00:00 +0900
categories:
  - python
tags:
  - Python
  - try-except
---
## 들어가며
Python에서 웹 스크레이핑이나 API를 호출할 때 많이 사용하는 라이브러리 중 하나는 `requests` 모듈입니다. 이 모듈을 사용하면서 발생할 수 있는 여러 가지 에러를 어떻게 처리하는 것이 좋은지 알아보겠습니다.

## try-except 블록 소개
`try-except` 블록은 Python에서 에러를 잡아내거나 처리할 때 사용하는 문법입니다. `try` 블록 안에는 에러가 발생할 가능성이 있는 코드를 넣고, `except` 블록 안에는 에러가 발생했을 때 실행할 코드를 넣습니다.

## 일반적인 에러 유형과 처리 방법

### `ConnectionError`
이 에러는 서버에 연결할 수 없을 때 발생합니다. 이 경우, 사용자에게 서버 연결 문제가 있다고 알려주는 것이 좋습니다.

```python
try:
    response = requests.get('http://example.com')
except requests.exceptions.ConnectionError:
    print("서버에 연결할 수 없습니다.")
```

### `Timeout`
`Timeout`은 서버에서 응답이 너무 늦게 오는 경우 발생합니다. 이때는 재시도하거나 다른 작업을 수행할 수 있습니다.

```python
try:
    response = requests.get('http://example.com', timeout=5)
except requests.exceptions.Timeout:
    print("요청 시간이 초과되었습니다.")
```

### `RequestException`
이는 모든 `requests` 에러의 기본 클래스입니다. 위의 예외들을 제외한 다른 에러를 잡을 때 사용할 수 있습니다.

```python
try:
    response = requests.get('http://example.com')
except requests.exceptions.RequestException as e:
    print(f"요청 중 에러가 발생했습니다: {e}")
```

## 에러를 미리 방지하기
에러를 미리 방지하는 좋은 방법 중 하나는 `if` 문을 사용해 `response.status_code`를 확인하는 것입니다. 200번대 코드가 오면 성공, 그 외는 실패로 간주할 수 있습니다.

```python
response = requests.get('http://example.com')
if response.status_code == 200:
    print("성공!")
else:
    print("요청 실패!")
```

## 마치며
`requests` 모듈을 사용하면서 발생할 수 있는 에러를 잘 처리하려면 `try-except` 블록을 적절하게 사용해야 합니다. 이를 통해 더 안정적인 프로그램을 만들 수 있습니다.