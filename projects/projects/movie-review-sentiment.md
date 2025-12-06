---
layout: project
title: 영화 리뷰 감성 분석
permalink: /projects/movie-review-sentiment/
order: 2
---

<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 말풍선 아이콘 -->
    <svg viewBox="0 0 24 24" width="32" height="32">
      <path d="M4 5h16v9a3 3 0 0 1-3 3H9l-4 3v-3H5a1 1 0 0 1-1-1V5z"
            fill="url(#sentGrad)"/>
      <defs>
        <linearGradient id="sentGrad" x1="0" y1="0" x2="1" y2="1">
          <stop offset="0%" stop-color="#ec4899"/>
          <stop offset="100%" stop-color="#6366f1"/>
        </linearGradient>
      </defs>
    </svg>
  </div>

  <h1>영화 리뷰 감성 분석</h1>
  <p class="mini-hero-sub">
    텍스트 데이터 전처리와 감성 분류 모델을 실습해본 NLP 기초 프로젝트
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Overview</h2>
  <p>
    영화 리뷰 데이터를 이용해 각 리뷰가 긍정인지 부정인지 분류하는 감성 분석 모델을 만드는 프로젝트다.
    자연어처리(NLP) 입문을 목표로, 전처리부터 피처 추출, 분류기 학습까지 한 번에 경험하는 것을 목표로 했다.
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Preprocessing & Features</h2>
  <p>
    텍스트 정제 과정에서는 소문자 변환, 불용어 제거, 구두점 제거 정도를 수행했다.
    그 이후에는 단어 빈도 기반의 Bag-of-Words와 TF-IDF 벡터를 각각 만들어 보고,
    어떤 방법이 더 성능이 잘 나오는지 비교했다.
  </p>
  <p>
    모델은 처음에는 로지스틱 회귀와 SVM 같은 전통적인 머신러닝 모델을 사용했고,
    이후 간단한 RNN 기반 모델도 시도하여 차이를 확인했다.
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Results & Discussion</h2>
  <p>
    TF-IDF + 로지스틱 회귀 조합에서 비교적 안정적인 성능이 나왔고,
    RNN 모델은 세부 튜닝에 따라 성능 편차가 컸다.
    데이터 전처리 방식과 하이퍼파라미터에 따라 결과가 얼마나 달라지는지 체감할 수 있었다.
  </p>
  <p>
    단순 정확도뿐 아니라 Precision, Recall, F1-score도 함께 확인하면서
    불균형 데이터에서 어떤 지표를 봐야 하는지도 연습했다.
  </p>
</div>
