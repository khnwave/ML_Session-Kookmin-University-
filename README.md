# Machine Learning Sessions

### Bank Marketing Classification | Kookmin University

국민대학교 머신러닝 세션에서 진행한 **은행 마케팅 반응 예측 분류 실험**을 정리한 저장소입니다. 데이터 탐색부터 피처 엔지니어링, 모델 학습, 하이퍼파라미터 최적화, 앙상블까지의 학습·실험 과정을 단계별로 기록했습니다.

> **Repository type:** 학습 및 실험 아카이브  
> **Main task:** Tabular binary classification  
> **Primary tools:** Python · Jupyter Notebook · LightGBM · Optuna · scikit-learn

---

## 01. Project Overview

은행의 텔레마케팅 관련 고객·캠페인 데이터를 활용해 **마케팅 반응(`label`)을 분류하는 모델**을 탐색합니다. 단일 모델을 구현하는 데 그치지 않고, 전처리 및 파생변수 구성, 학습 방식, 파라미터 탐색, 앙상블 전략을 달리하며 결과를 비교할 수 있도록 실험 기록을 보존했습니다.

| 항목 | 내용 |
| --- | --- |
| 데이터 | 은행 마케팅 관련 고객 및 캠페인 데이터 (`data/train.csv`, `data/test.csv`) |
| 예측 대상 | `label` |
| 주요 입력 변수 | 나이, 직업, 교육, 잔고, 대출, 연락·캠페인 이력 등 |
| 문제 유형 | 이진 분류 |
| 주요 시도 | Baseline → Feature Engineering → LightGBM → GridSearch/Optuna → Ensemble |

※ 이 저장소의 제출 CSV와 노트북은 **실험 기록**입니다. 최종 성능 및 최적 모델은 별도 재검증하지 않았으므로 특정 점수나 순위를 확정적으로 기재하지 않았습니다.

## 02. Machine Learning Workflow

```text
Data Exploration
       ↓
Data Preprocessing & Feature Engineering
       ↓
Baseline / LightGBM Modeling
       ↓
Hyperparameter Tuning (GridSearch, Optuna)
       ↓
Ensemble & Sampling Experiments
       ↓
Prediction Files / Experiment Review
```

각 단계의 폴더는 **학습 흐름에 따라 탐색하기 쉽도록 재배치한 분류**이며, 모든 노트북이 단일 파이프라인에서 순차 실행되도록 작성된 것은 아닙니다.

## 03. Repository Structure

```text
.
├── 01_EDA/                    # 변수 분포, 데이터 구조 등 탐색적 분석
├── 02_Feature_Engineering/    # 전처리 및 특성 구성 실험
├── 03_Modeling/               # Baseline, LightGBM 모델링
├── 04_Hyperparameter_Tuning/  # GridSearch 및 Optuna 실험
├── 05_Ensemble/               # 앙상블 및 샘플링 접근
├── 06_Experiments/            # try_01~try_04 및 후속 실험 기록
├── 07_Results/                # 제출용 예측 CSV 및 중간 결과
├── 08_References/             # 참고 노트북·발표 자료
├── config/                    # 하이퍼파라미터 설정 JSON
├── data/                      # 로컬 학습·테스트 CSV
├── FILE_MAP.md                # 원본 파일명 ↔ 정리된 파일 경로
└── README.md
```

## 04. Recommended Reading Path

처음 방문했다면 아래 순서로 보는 것을 추천합니다.

| 순서 | 추천 파일 | 살펴볼 내용 |
| :---: | --- | --- |
| 1 | [`01_EDA/`](01_EDA/) | 데이터 및 변수 분포 탐색 |
| 2 | [`03_Modeling/baseline.ipynb`](03_Modeling/baseline.ipynb) | 기준 모델 및 기본 학습 흐름 |
| 3 | [`02_Feature_Engineering/`](02_Feature_Engineering/) | 전처리·피처 엔지니어링 시도 |
| 4 | [`03_Modeling/LGBM_try1.ipynb`](03_Modeling/LGBM_try1.ipynb) | LightGBM 기반 모델링 |
| 5 | [`04_Hyperparameter_Tuning/`](04_Hyperparameter_Tuning/) | GridSearch와 Optuna 기반 탐색 |
| 6 | [`05_Ensemble/`](05_Ensemble/) | 앙상블 및 샘플링 실험 |
| 7 | [`06_Experiments/`](06_Experiments/) | 여러 실험 버전과 추가적인 개선 시도 |
| 8 | [`07_Results/`](07_Results/) | 실험별 예측·제출 파일 |

### Notebooks to explore

- **Baseline:** [`baseline.ipynb`](03_Modeling/baseline.ipynb)
- **Feature Engineering:** [`FE_lgbm.ipynb`](02_Feature_Engineering/FE_lgbm.ipynb)
- **LightGBM:** [`LGBM_try2.ipynb`](03_Modeling/LGBM_try2.ipynb)
- **Optuna:** [`Ho_Optuna_try2.ipynb`](04_Hyperparameter_Tuning/Ho_Optuna_try2.ipynb)
- **Ensemble:** [`PA+ENSANBLE.ipynb`](05_Ensemble/PA%2BENSANBLE.ipynb)

## 05. Experiments & Outputs

`06_Experiments/`에는 `try_01`부터 `try_04`까지의 실험과 변형 버전을 보존했습니다. 비슷한 이름의 노트북도 서로 다른 전처리, 설정 또는 실험 과정을 포함할 수 있어 기록을 임의로 합치지 않았습니다.

`07_Results/`에는 실험별 제출용 CSV가 있습니다. **파일명이 `final`이라고 해서 외부 평가 기준으로 최고의 성능임을 의미하지는 않습니다.** 정확한 성능 비교를 위해서는 노트북의 검증 지표, 데이터 분할, 실행 조건을 함께 확인해야 합니다.

## 06. Running Locally

```bash
# Clone this repository
git clone https://github.com/khnwave/ML_Session-Kookmin-University-.git
cd ML_Session-Kookmin-University-

# Create a virtual environment (macOS / Linux)
python3 -m venv .venv
source .venv/bin/activate

# Launch Jupyter (after installing the required packages)
jupyter lab
```
