# Team_F

## 사용한 데이터

- **분석에 실제 사용된 전처리 데이터**:  
  [https://github.com/seojincho77/Team_F/releases/tag/v1.0.0](https://github.com/seojincho77/Team_F/releases/tag/v1.0.0)  
  (전처리된 관객/평론가 리뷰 데이터 포함)
  <sub>데이터 파일 용량 문제로 별도 업로드하였습니다.</sub>
---

### 원본 데이터 출처

- IMDB Movie Reviews Dataset (관객 리뷰):  
  https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews

- Rotten Tomatoes Critic Reviews Dataset (평론가 리뷰):  
  https://www.kaggle.com/datasets/stefanoleone992/rotten-tomatoes-movies-and-critic-reviews-dataset
  

### 1. `audience_review_topic_analysis.ipynb`
IMDB 데이터셋을 기반으로 **관객 리뷰의 감정별 주요 키워드**를 추출하고 분석합니다.

- **사용 데이터**: `IMDB Dataset.csv` (전처리된 버전: `cleaned_imdb_reviews.csv`)
- **주요 과정**:
  - 텍스트 전처리 (HTML 제거, 축약어 복원, 불용어 제거, 어간 추출 등)
  - 감정 구분: 긍정 / 부정
  - 명사/형용사 기반 키워드 필터링 및 빈도 분석
  - 상위 키워드 시각화

---

### 2. `critic_review_topic_analysis.ipynb`
Rotten Tomatoes의 평론가 리뷰 데이터를 기반으로 **감정별 주요 키워드**를 추출하여 분석합니다.

- **사용 데이터**: `rotten_tomatoes_critic_reviews.csv` (전처리된 버전: `cleaned_rotten_tomatoes_critic_reviews.csv`)
- **주요 과정**:
  - 리뷰 전처리 및 정규화
  - 감정 라벨링 (`Fresh` → 긍정, `Rotten` → 부정)
  - 품사 기반 키워드 필터링
  - 각 감정군의 빈도 상위 키워드 도출

---

### 3. `sentiment_agreement_check.ipynb`
관객과 평론가의 감정 분류 결과를 **모델을 통해 비교 분석**하고, 감정 인식의 일치 정도를 파악합니다.

- **분석 방식**:
  - 관객 리뷰와 평론가 리뷰 각각에 대해 Word2Vec 임베딩 생성
  - 랜덤 포레스트 분류기를 통해 감정 분류 모델 학습
  - 분류 정확도 측정 및 향후 감정 일치율 분석 기반 마련

---

## 분석 목적
관객과 평론가가 **같은 영화를 어떻게 다르게 받아들이는가**를 분석하고, 감정 분석 결과가 얼마나 일치하는지를 확인함으로써 **예술성과 대중성의 차이 또는 교집합**을 찾아내는 것이 궁극적인 목적
