# Aircraft Engine Predictive Maintenance & GenAI Assistant

## Project Overview
항공기 엔진 센서 데이터를 분석하여 잔여 수명(RUL, Remaining Useful Life)을 예측하고, 예측 결과를 바탕으로 LLM 기반의 자동화된 정비 가이드를 생성하는 프로젝트입니다. 
단순 고장 예측을 넘어, 예지 보전(Predictive Maintenance) 시스템과 생성형 AI를 결합하여 유지보수 비용을 최적화하고 엔지니어의 의사결정을 지원하는 파이프라인을 구축했습니다.

## Business Impact
* 운영 효율화: 대규모 시계열 데이터 분석을 통해 사전 정비 시기를 도출하여 예기치 않은 비행 지연(Downtime) 방지.
* 프로세스 자동화: 예측된 RUL 수치를 기반으로 LangChain과 Vertex AI를 활용해 맞춤형 정비 리포트 자동 생성.

## Tech Stack
* Data Science & ML: Python, Pandas, Scikit-learn, XGBoost
* AI Engineering: LangChain, Google Vertex AI (Gemini)
* Domain: Time-series Analysis, Predictive Maintenance

## Key Features
1. Data Preprocessing & EDA: 다중 센서 데이터의 노이즈 제거 및 시계열 이동 평균(Rolling Mean) 특성 추출.
2. RUL Prediction Model: XGBoost 회귀 모델을 활용한 엔진별 고장 도달 비행 횟수(Cycle) 예측.
3. Automated Maintenance Report (GenAI): 예측된 고장 위험도에 따라 정비사에게 필요한 조치 사항을 LLM으로 자동 요약 및 브리핑.

## Purpose
RUL(잔여 수명) 예측 모델과 LLM을 결합한 데이터 처리 파이프라인 구현을 목적으로 합니다.
