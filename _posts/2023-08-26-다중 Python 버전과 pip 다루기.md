---
title: 다중 Python 버전과 pip 다루기
date: 2023-08-26 20:00:00 +0900
categories:
  - python
tags:
  - 다중Python
  - pip
---
# 다중 Python 버전과 pip 다루기

## 문제의 본질: 여러 Python 버전과 pip 충돌

먼저, 여러 Python 버전이 설치된 시스템에서 pip를 사용할 때 발생하는 문제점을 이해해야 합니다. 가장 일반적인 문제는 `pip` 명령어가 어떤 Python 버전과 연결되어 있는지 모르는 상황입니다. 이로 인해 원치 않는 Python 버전에 패키지가 설치될 수 있습니다.

## 해결 방안 1: 명시적 Python 버전 사용

첫 번째 해결 방안은 `python` 대신에 명시적으로 Python 버전을 적는 것입니다. 예를 들어, Python 3.8을 사용한다면, `python3.8 -m pip install 패키지이름` 명령어를 사용할 수 있습니다. 이렇게 하면 Python 3.8 버전에 해당 패키지가 설치됩니다.

## 해결 방안 2: 가상 환경 사용

두 번째 해결 방안은 Python 가상 환경을 사용하는 것입니다. 가상 환경은 특정 프로젝트에 필요한 패키지와 의존성을 따로 관리해줍니다. `venv` 라는 모듈을 사용해서 가상 환경을 만들 수 있습니다. 가상 환경을 활성화한 상태에서 `pip install` 명령어를 사용하면 해당 환경에만 패키지가 설치됩니다.

## 해결 방안 3: `pipx` 사용

세 번째 해결 방안은 `pipx`를 사용하는 것입니다. `pipx`는 각각의 Python 패키지를 독립적인 환경에서 실행할 수 있도록 해줍니다. 이렇게 하면 여러 Python 버전 간의 충돌 없이 특정 버전의 패키지를 사용할 수 있습니다.

## 코드에서 발생할 수 있는 오류: `ModuleNotFoundError`

여러 Python 버전을 사용하다 보면 `ModuleNotFoundError`라는 오류가 발생할 수 있습니다. 이 오류는 특정 Python 버전에서 필요한 모듈이 설치되지 않았을 때 나타납니다.

## 결론

여러 Python 버전과 pip를 함께 사용할 때 문제를 해결하는 방법은 여러 가지입니다. 명시적인 Python 버전 사용, 가상 환경, 그리고 `pipx` 사용 등 다양한 방법으로 이 문제를 극복할 수 있습니다. 선택할 방법은 개발 환경과 필요에 따라 달라질 수 있으니, 상황에 맞게 적절한 방법을 선택하면 됩니다.