# 원마트 데이터를 활용한 고객 구매 패턴 기반 멤버십과 맞춤형 알림 서비스를 통한매출 증대 방안
- 디지털하나로_미니 프로젝트(2차)_Team 세(3)계로
- **주요 내용**
  - 연관 분석(Association Analysis) : mlxtend 패키지를 통한 Aproiri(연관분석/장바구니분석) 알고리즘​ 적용
  - 고객 RFM 분석
  - 확증적 데이터분석(CDA) : ‘방문 횟수’와 ‘모바일알람여부’ 사이의 정규성 및 ranksum 검정

***
## 0. Stacks
>|⚙️Skill & Environment|🗣️Coummnication|
>|:------------------:|:-------------:|
>|![Python](https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white) ![Jupyter Notebook](https://img.shields.io/badge/jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white) ![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=Git&logoColor=white) ![Github](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white)|![Slack](https://img.shields.io/badge/Slack-4A154B?style=for-the-badge&logo=Slack&logoColor=white) ![Notion](https://img.shields.io/badge/Notion-000000?style=for-the-badge&logo=Notion&logoColor=white) ![GoogleMeet](https://img.shields.io/badge/GoogleMeet-00897B?style=for-the-badge&logo=Google%20Meet&logoColor=white)|


<br />

## 1. 프로젝트 소개
- 디지털하나로 미니프로젝트(2차)
- 고객 데이터와 상품 구매 데이터를 활용
- RFM 분석을 바탕으로 고객 등급을 세분화(A/B/C/D)하여 등급 별 구매 패턴 파악 및 비교
- 멤버십 등급별 맞춤 알림 서비스 제공을 위해 RFM 분석 기반 가설 검정 및 Apriori 알고리즘을 통해 구매상품의 유의미한 연관규칙 도출 및 연관 상품 추천 서비스

<br />

## 2. 프로젝트 목표
### (1) 비즈니스 목표 및 KPI
  | 방문횟수와 매출액 사이 회귀분석 기반 매출 증가 KPI목표 |
  | :-------------------------------------------: |
  | <img width="685" alt="image" src="https://github.com/user-attachments/assets/267ce7b4-2226-457c-be7e-b8eb31ea11c2"> |
  
### (2) 데이터분석 목표
  | 1. 기존 불균형한 고객 등급 체계 개편 - RFM 분석 | 2. 온라인 알림 서비스개편 - 연관 분석 |
  | :------------------------------------: | :---------------------------: |
  | <img width="330" alt="image" src="https://github.com/user-attachments/assets/8336e012-f39f-4e13-a8a1-761b3bcb0bdf"> | <img width="330" alt="image" src="https://github.com/user-attachments/assets/91958594-3acf-4d72-8deb-69218db136a8"> |

<br />

## 3. 데이터분석 계획
  | (1)멤버십 개편 : 고객 RFM 분석 및 재편성 |
  | :-------------------------------------------: |
  | <img width="685" alt="image" src="https://github.com/user-attachments/assets/645ca3e8-ed04-4e9c-93b4-932672ff19b2"> |
  | **(2)알림서비스 개편 : CDA와 연관분석 활용** |
  | <img width="686" alt="image" src="https://github.com/user-attachments/assets/712e3666-6b3e-4274-916b-2ee93e8ab2e7"> |


<br />

## 4. 데이터분석
#### 0. 데이터셋
- 프로젝트용으로 제공받음(비공개)

#### 1. 필요 패키지
- (1) 패키지 설치
  ```python
  !pip install mlxtent #설치
  !pip install mlxtend --upgrade #or 업그레이드
  ```
- (2) 연관분석 필요 패키지
  ```
  from mlxtend.frequent_patterns import apriori, association_rules
  from mlxtend.preprocessing import TransactionEncoder
  ```

#### 2. 프로젝트 설명 및 개발 환경
- 개발 환경
  - python : 3.8.3
  - jupyter notebook : 6.0.3
  - mlxtend : 0.17.3

#### 3. 수행 결과
  - 상위 10개 규칙 결과
  ```
    # 규칙을 confidence(신뢰도) 값으로 내림차순 정렬.
    rules_sorted = rules.sort_values(by=['confidence'], ascending=False)
  ```
  <img width="1353" alt="image" src="https://github.com/user-attachments/assets/cb9680be-fb24-42e0-8c2b-93ee61606795">

