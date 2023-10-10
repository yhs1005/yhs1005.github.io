---
title: Python의 Easy Install로 설치한 패키지 제거 방법
date: 2023-08-30 20:00:00 +0900
categories:
  - python
tags:
  - Python
  - EasyInstall
---
## 소개
Python에서는 다양한 패키지를 쉽게 설치할 수 있게 해주는 몇 가지 도구가 있습니다. 그 중 하나가 `easy_install`인데, 이 도구로 설치한 패키지를 어떻게 제거할지에 대해 알아보겠습니다. 

## easy_install이란?
`easy_install`은 Python 패키지를 설치하기 위한 소프트웨어 도구입니다. 이 도구는 과거에 많이 사용되었지만 현재는 `pip`에게 그 자리를 내주고 있습니다. 여기서 '패키지'라는 것은 Python 프로그램에서 사용할 수 있는 외부 기능들을 모아놓은 것을 말합니다.

## easy_install로 설치한 패키지 제거
`easy_install`로 설치한 패키지를 제거하는 과정은 다소 복잡할 수 있습니다. 직접 파일을 찾아서 제거해야 할 가능성이 높습니다.

### 단계 1: 패키지 목록 확인
먼저 설치된 패키지의 목록을 확인합니다. 이 목록은 일반적으로 `site-packages` 디렉터리에 위치합니다.

```bash
ls /path/to/site-packages/
```

### 단계 2: 파일 제거
`site-packages` 디렉터리에서 해당 패키지와 관련된 모든 파일과 폴더를 찾아서 제거합니다.

```bash
rm -rf /path/to/site-packages/PackageName
```

### 단계 3: egg-info 제거
마지막으로 `.egg-info` 파일도 제거해야 합니다.

```bash
rm /path/to/site-packages/PackageName.egg-info
```

## 주의사항
위의 방법은 수동적인 방법입니다. 더 안전하고 쉬운 방법을 원한다면 `pip`를 사용하여 패키지를 제거하는 것이 좋습니다.

## 결론
`easy_install`로 설치한 패키지를 제거하는 것은 직접 파일을 찾아 삭제하는 수동적인 방법을 사용해야 할 수도 있습니다. 더 쉽고 안전한 방법을 원한다면 `pip`를 사용하는 것이 좋습니다. 이 기사를 통해 패키지를 어떻게 제거하는지에 대한 명확한 방법을 알게 되었기를 바랍니다.