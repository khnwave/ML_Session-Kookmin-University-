# Machine Learning Session | Bank Marketing Classification

머신러닝 학습 및 Kaggle 실험 아카이브입니다. 탐색적 데이터 분석(EDA), 피처 엔지니어링, 모델링, 하이퍼파라미터 튜닝, 앙상블 등 **실험 단계**에 따라 노트북을 분류했습니다.

> 이 저장소는 기존 학습 노트북의 정리본입니다. 결과 성능, 모델 실행 환경, 모든 파일의 재현 가능성은 아직 별도로 검증하지 않았습니다.

## Repository structure

```text
ML_Session_GitHub/
├── 01_EDA/                     # 탐색적 분석
├── 02_Feature_Engineering/     # 변수 생성 및 전처리
├── 03_Modeling/                # Baseline / LightGBM
├── 04_Hyperparameter_Tuning/   # GridSearch / Optuna
├── 05_Ensemble/                # Ensemble / Resampling
├── 06_Experiments/             # try_01 ~ try_04 및 실험 변형
├── 07_Results/                 # 제출용 예측 CSV
├── 08_References/              # 강의자료 및 별도 참고 노트북
├── config/                     # 학습 파라미터
├── data/                       # 원본 CSV (라이선스 및 공개 가능 여부 확인 필수)
├── FILE_MAP.md                 # 원본 파일 → 정리된 파일 경로
└── .gitignore
```

## Suggested reading order

1. `01_EDA`에서 데이터 구조 및 분포 살펴보기
2. `02_Feature_Engineering`에서 전처리/파생변수 살펴보기
3. `03_Modeling`에서 베이스라인과 트리 기반 모델 비교
4. `04_Hyperparameter_Tuning`에서 튜닝 방법 확인
5. `05_Ensemble`에서 모델 조합 및 샘플링 실험 확인
6. `06_Experiments`에서 시도별 기록 검토

## Before publishing

- `data/`의 데이터 라이선스·개인정보·공개 가능 범위 확인
- 노트북 출력에 포함된 개인 정보, 토큰, 로컬 경로 제거
- 제출 파일에 비공개 정보가 없는지 확인
- 각 노트북의 실행 경로를 `data/`에 맞게 수정한 후 재실행
- 성능 수치는 교차검증 방식·평가지표와 함께 검증 후 기재
