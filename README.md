# 선박 목적지·도착예정시간(ETA) 예측

AIS(선박자동식별) 항적 데이터로 선박의 **목적지 항구**와 **도착예정시간(ETA)** 을 예측하는 모델이다.
해운물류 프로젝트에서 개발했으며, 저장소에는 전처리·모델 코드만 담았다. (데이터는 제외)

<br>

## 접근

- **전처리** : 1년치 AIS 항적 + 화물·항구 데이터 통합, 연도별 병합
  - `notebooks/ais.ipynb`, `ais_analysis.ipynb`, `preprocess-data.ipynb`
- **그리드 매핑** : 위경도 좌표를 격자(grid)로 변환
  - `map_to_grid.py`, `notebooks/map_to_grid.ipynb`
- **ETA 예측 (LSTM)** : 항해시간 시계열 예측
  - `notebooks/Predict_eta(최종).ipynb`, `predictETA_3.ipynb`, `PREDICT_MODEL.ipynb`
- **목적지 예측 (Random Forest)** : 도착 항구 분류
  - `notebooks/destPredict.ipynb`, `2020721_destPredict.ipynb`

<br>

## 메모

- 노트북은 용량을 줄이기 위해 출력(output)을 지운 상태다.
- 원본 AIS·화물·항구 데이터(CSV)는 포함하지 않는다.

<br>

## 기술 스택

Python · TensorFlow/Keras(LSTM) · scikit-learn(Random Forest) · Pandas
