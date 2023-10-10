---
title: Python의 requirements.txt에서 GitHub 소스 지정하기
date: 2023-09-17 20:00:00 +0900
categories:
  - python
tags:
  - requirements
  - GitHub
  - Python
---
## 문제상황: requirements.txt에 GitHub 레포지토리 지정

Python 프로젝트를 관리할 때 종종 `requirements.txt` 파일을 사용하여 필요한 패키지를 명시합니다. 하지만 이 파일에서 직접 GitHub 소스를 지정하는 방법은 약간 복잡할 수 있습니다. 이 문제는 특히 공식 패키지 저장소에 없는 패키지를 GitHub에서 직접 설치해야 할 경우에 자주 발생합니다.

## 해결방안: GitHub URL을 이용한 패키지 지정

`requirements.txt`에서 GitHub의 레포지토리를 직접 지정하는 방법은 아래와 같습니다.

1. **일반적인 형식**: GitHub 레포지토리의 URL을 사용해 패키지를 지정할 수 있습니다. 
    ```
    git+https://github.com/유저이름/레포지토리이름.git
    ```

2. **브랜치 지정**: 특정 브랜치를 지정하려면 `@` 기호와 브랜치 이름을 추가합니다.
    ```
    git+https://github.com/유저이름/레포지토리이름.git@브랜치이름
    ```
   
3. **태그 지정**: 특정 태그를 지정하려면 `#egg=`을 사용해 패키지 이름과 버전을 명시합니다.
    ```
    git+https://github.com/유저이름/레포지토리이름.git#egg=패키지이름-버전
    ```

예를 들어, GitHub에서 `some-package`라는 이름의 패키지를 `dev` 브랜치에서 설치하려면 다음과 같이 작성합니다.
```
git+https://github.com/username/some-package.git@dev
```

## 주의사항: 문제 해결 중 발생할 수 있는 오류

1. **`CloningError`**: 이 오류는 대게 레포지토리 URL이 잘못되었을 때 발생합니다. URL을 다시 확인해주세요.

2. **`BranchDoesNotExist`**: 지정한 브랜치가 존재하지 않을 때 발생하는 오류입니다. 브랜치 이름을 정확하게 입력했는지 확인해주세요.

이 글을 통해 `requirements.txt`에서 GitHub 소스를 어떻게 지정하는지에 대한 명확한 가이드라인을 얻으셨기를 바랍니다. 이 방법을 사용하면 공식 패키지 저장소에 없는 패키지도 손쉽게 설치할 수 있습니다.