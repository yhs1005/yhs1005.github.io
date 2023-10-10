---
title: Pandas로 여러 CSV 파일 합치기
date: 2023-09-22 20:00:00 +0900
categories:
  - python
tags:
  - Pandas
  - CSV
---
## 문제 상황

판다스(Pandas) 라이브러리를 사용하여 여러 CSV 파일을 하나의 데이터프레임(DataFrame)으로 병합(Concatenate)하려고 할 때 어떻게 해야 하는지 궁금하다면, 이 글은 여러분을 위한 것입니다. 

## `pd.concat()` 함수 사용법

판다스의 `pd.concat()` 함수를 사용하면 이 작업을 간단히 수행할 수 있습니다. `pd.concat()` 함수는 여러 데이터프레임을 하나로 합치는 역할을 합니다.

### 예시 코드

```python
import pandas as pd
import glob

path = 'your_directory/*.csv'
files = glob.glob(path)

dataframes = [pd.read_csv(f) for f in files]
merged_dataframe = pd.concat(dataframes, ignore_index=True)
```

## 코드 분석

- `import pandas as pd`: 판다스 라이브러리를 불러옵니다.
- `import glob`: 파일 경로를 쉽게 찾을 수 있도록 `glob` 모듈을 불러옵니다.
- `path = 'your_directory/*.csv'`: 병합하려는 CSV 파일들이 있는 디렉터리를 지정합니다.
- `files = glob.glob(path)`: 지정한 디렉터리의 모든 CSV 파일을 찾아 리스트에 저장합니다.
- `dataframes = [pd.read_csv(f) for f in files]`: 각 파일을 데이터프레임으로 읽어 리스트에 저장합니다.
- `merged_dataframe = pd.concat(dataframes, ignore_index=True)`: 모든 데이터프레임을 하나로 병합합니다. `ignore_index=True` 옵션을 사용하여 새로운 인덱스를 생성합니다.

## 주의사항

- 모든 CSV 파일은 같은 디렉터리에 위치해야 합니다.
- `ignore_index=True` 옵션은 기존 인덱스를 무시하고 새로운 인덱스를 생성합니다. 이 옵션이 필요 없다면 생략할 수 있습니다.

## 결론

판다스의 `pd.concat()` 함수와 `glob` 모듈을 사용하면 여러 CSV 파일을 쉽게 하나의 데이터프레임으로 병합할 수 있습니다. 이 방법은 데이터 분석이나 머신 러닝 작업에서 자주 사용되므로 유용하게 활용할 수 있습니다.