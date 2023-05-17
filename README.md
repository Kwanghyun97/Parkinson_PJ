# Parkinson Project (2023.04.24 ~ 2023.05.17)

[대시보드 링크](https://kwanghyun97-parkinson-pj-app-oc2h0c.streamlit.app/) <br/><br/>
[발표 영상] <br/><br/>
[데모 시연] <br/><br/>
[PPT](pdf/2조_파킨슨_질병_진단예측.pdf)<br/><br/>


## 대회 이름
**AMP®-Parkinson's Disease Progression Prediction**

## 목적
이 대회의 목적은 **파킨슨병 환자의 임상 데이터**를 사용하여, 파킨슨병 환자의 진행을 측정하는 **MDS-UPDRS (통합 파킨슨병 평가척도) 예측**

## 데이터
Kaggle 에서 제공하는 데이터를 사용하였습니다.

[대회 URL](https://www.kaggle.com/competitions/amp-parkinsons-disease-progression-prediction)

## 팀 구성
- 사용언어 : Python : 3.9.13v
- 작업툴 : google Colab, pycharm, Stream
- 인원 : 4명
- 주요 업무 : Streamlit 라이브러리를 이용한 웹개발 구현 코드 작성 및 머신러닝을 활용한 **MDS-UPDRS (통합 파킨슨병 평가척도) 예측**
- 기간 : 2023-04-24 ~ 2023-05-17
***

## 대시보드 주요기능
### 메인 메뉴 구성
[**대시보드 URl**](https://kwanghyun97-parkinson-pj-app-oc2h0c.streamlit.app/)  
- **Home**
    - 대회 목표 및 대회 개요
- **Description**
    - 대회를 위한 도메인 지식 용어 설명 EX) Parkison 이란 ?, MDS-UPDRS 란 ? 
    - 사용한 주평가지표 설명(SMAPE)
- **DATA**
    - DATA Columns 에 대한 설명
    - DATA Set 구조 확인
- **EDA**
    - 자료탐색과 이해를 위한 데이터 시각화 EX) Mean UPDRS Scores by Visit_Month...
    - Clinical / Supplimental Clinical | Protein / Peptides 데이터별 구분
- **STAT** 
    - 두 집단의 평균비교 (t-test) 시각화 및 설명
    - 약물 복용에 따른 UPDRS Score 비교
    - 귀무가설(H0) : 두 모집단 (On, Off) 평균이 같다
    - 대립가설(H1) : 두 모집단 (On, Off) 평균이 같지 않다
    - p-value < 0.05 귀무가설(H0) 기각  /  대립가설(H1) 채택 -> On, Off 의 평균이 다르다고 판단 할 수 있음
- **ML** 
    - CatBoost 관련 설명
    - K-fold(5) 교차 검증 설명 및 예측값, 실제값 시각화 그래프
    - 모델 별 SMAPE Score 및 시각화
    - 캐글 최종 제출 Score 및 등수 기재
 
## 분석 Flow
[PPT 자료 Link](pdf/2조_파킨슨_질병_진단예측.pdf)
- **프로젝트 팀 구성**
    - 팀구성 및 역활
    - 개발 환경
    - 프로젝트 기간
- **프로젝트 개요**
    - 대회 목적
    - 연구 배경
    - 평가 지표
    - 순서도
- **프로젝트 수행 절차**     
    - 테이블 정의서
    - 데이터 전처리
    - 피처 엔지니어링
- **수행결과 1**
    - 기초통계분석
    - 머신러닝
    - 데이터 분석
    - 모델 생성 및 학숩
    - 모델 평가 및 성능 검증       
- **수행결과 2**      
    - 대시보드 소개
- **자체 평가 의견**       
    - 분석 결과 요약
    - 한계점 및 개선 사항

## 분석 결과
    - 단일 펩타이드와 단일 단백질로는 UPDRS의 점수와 명확한 관계가 있다고 보기 어려움
    - 제공 된 데이터에서는 peptide,  protein의 정보보다 피험자의 수(patient_id)가 더 중요
    - UPDRS_4는 다른 UPDRS보다 데이터가 더 부족하기 때문에, UPDRS_4의 값을 0으로 설정했을 때 예측 값이 더 높게 나타남
    - 약물을 복용한 사람들이 복용하지 않은 사람들 보다 비교적 느리게 질병이 진행 됨 그러나 시간이 지날수록 둘 다 UPDRS의 점수는 증가


## 팀이 공통적으로 느낀 한계점
    - protein 데이터가 visit_month의 최대 40%만 존재하여, 정확한 데이터를 확보했다고 보기 어려움
    - protein, pepetide의 데이터보다 약물복용여부가 더 중요하다고 판단이 되지만, test_data에서는 약물 복용 여부를 알 수 없음
    - 여러가지 모델을 구현 하는 데에 있어 한계가 있음
    - 평가지표(SMAPE)의 결과값이 대부분 높은 수치를 보이며 SMAPE가 모델 평가에 가장 적합한 평가지표가 맞는지 비교해볼 필요가 있음.

