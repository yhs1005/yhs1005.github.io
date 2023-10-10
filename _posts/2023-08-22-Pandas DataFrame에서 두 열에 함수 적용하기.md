---
title: Pandas DataFrame에서 두 열에 함수 적용하기
date: 2023-08-22 09:00:00 +0900
categories:
  - python
tags:
  - Pandas
  - DataFrame
---
## 개요

Pandas는 데이터 처리와 분석에 사용되는 Python 라이브러리입니다. 이 라이브러리는 다양한 데이터 구조와 분석 도구를 제공하며, 특히 DataFrame이라는 2차원 표 구조를 사용하여 데이터를 쉽게 조작할 수 있습니다. 이 글에서는 Pandas DataFrame에서 두 열에 함수를 적용하는 방법에 대해 설명합니다.

## `apply` 메서드 이해하기

Pandas DataFrame에는 `apply`라는 메서드가 있습니다. 이 메서드를 사용하면 DataFrame의 행 또는 열에 함수를 적용할 수 있습니다. '메서드'란 객체에 특정 작업을 수행하는 함수를 의미합니다.

### 예제 코드

아래의 예제 코드를 보면, DataFrame의 'A' 열과 'B' 열에 더하기(`add`) 함수를 적용한 것을 확인할 수 있습니다.

```python
import pandas as pd

df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})
df['C'] = df.apply(lambda row: row['A'] + row['B'], axis=1)
```

이 코드에서 `lambda row: row['A'] + row['B']`는 간단한 무명 함수입니다. 이 함수는 각 행의 'A' 값과 'B' 값을 더하고 있습니다. `axis=1`은 함수가 행에 적용되어야 함을 의미합니다.

## 주의할 점과 Error 이름

이 방법을 사용할 때 주의해야 할 점은 모든 열이 같은 데이터 타입을 가져야 한다는 것입니다. 만약 이를 지키지 않으면 `TypeError`라는 오류가 발생할 수 있습니다.

## 요약

Pandas DataFrame에서 두 열에 함수를 적용하는 것은 `apply` 메서드를 사용하여 간단하게 수행할 수 있습니다. 이 메서드는 매우 유연하며 다양한 데이터 처리 작업에 활용될 수 있습니다. 주의해야 할 점은 열의 데이터 타입이 일치해야 한다는 것이며, 그렇지 않을 경우 `TypeError`가 발생할 수 있습니다.