---
title: TensorFlow에서 나타나는 'CPU Instructions' 오류 해결 방법
date: 2023-09-03 20:00:00 +0900
categories:
  - python
tags:
  - TensorFlow
  - CPU
  - Instructions
---
## 오류 정의: Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2

TensorFlow를 실행할 때마다 이러한 메시지가 나타날 수 있습니다. "Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2"라는 오류는 여러분의 CPU가 AVX2라는 명령어를 지원하는데, 설치된 TensorFlow 버전이 이를 활용하지 못하고 있다는 것을 의미합니다.

## AVX2가 무엇인가?

AVX2는 'Advanced Vector Extensions 2'의 약자로, CPU가 데이터를 더 빠르게 처리할 수 있도록 도와주는 기술입니다. 이 기능을 활용하지 않으면 성능이 저하될 수 있습니다.

## 해결 방법 1: TensorFlow 소스로부터 직접 빌드하기

TensorFlow를 소스 코드로부터 직접 빌드하면, 여러분의 시스템에 최적화된 버전을 얻을 수 있습니다. 이 방법은 시간이 많이 걸릴 수 있지만, 성능 향상이 기대됩니다.

1. TensorFlow의 GitHub 저장소를 클론합니다.
2. 빌드 환경을 설정합니다.
3. AVX2 명령어를 활용하도록 설정한 후 빌드를 진행합니다.

## 해결 방법 2: 오류 메시지 숨기기

성능 저하가 크게 문제가 되지 않는다면, 오류 메시지를 숨기는 방법도 있습니다. TensorFlow를 사용할 때 다음과 같은 코드를 추가하면 됩니다.

```python
import os
os.environ['TF_CPP_MIN_LOG_LEVEL'] = '2'
```

## 해결 방법 3: 다른 버전의 TensorFlow 설치하기

TensorFlow는 여러 버전이 있고, 일부 버전은 AVX2 명령어를 지원합니다. 다른 버전의 TensorFlow를 설치하여 문제를 해결할 수 있습니다.

## 결론

TensorFlow에서 "Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2" 오류는 여러 방법으로 해결할 수 있습니다. 가장 적합한 방법을 선택하여 성능을 최적화할 수 있습니다.