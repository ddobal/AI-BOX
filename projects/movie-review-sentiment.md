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

<!-- Overview -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h2>Overview</h2>
  <p>
    영화 리뷰 데이터를 이용해 각 리뷰가 긍정인지 부정인지 분류하는 감성 분석 모델을 만드는 프로젝트다.
    자연어처리(NLP) 입문을 목표로, 전처리부터 피처 추출, 분류기 학습까지 한 번에 경험하는 것을 목표로 했다.
  </p>
  <p>
    아래 도형은 텍스트 리뷰가 모델까지 전달되기까지의 전체 흐름을 한눈에 정리한 파이프라인이다.
  </p>
</div>

<!-- Diagram 1 : Sentiment Analysis Pipeline -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h3 style="margin-top:0;">Sentiment Analysis Pipeline</h3>

  <svg width="100%" height="260" viewBox="0 0 840 260">
    <!-- Raw Reviews -->
    <rect x="40" y="90" width="190" height="80" rx="12" fill="#020617" stroke="#ec4899" stroke-width="2"/>
    <text x="135" y="120" font-size="14" fill="#fdf2f8" text-anchor="middle">영화 리뷰 텍스트</text>
    <text x="135" y="140" font-size="11" fill="#f9a8d4" text-anchor="middle">긍정 / 부정 문장 섞여 있음</text>

    <!-- Arrow 1 -->
    <line x1="230" y1="130" x2="300" y2="130" stroke="#64748b" stroke-width="2"/>
    <polygon points="300,130 290,125 290,135" fill="#64748b"/>

    <!-- Preprocessing -->
    <rect x="300" y="70" width="200" height="120" rx="12" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="400" y="105" font-size="14" fill="#e5e7eb" text-anchor="middle">텍스트 전처리</text>
    <text x="400" y="125" font-size="11" fill="#c7d2fe" text-anchor="middle">
      소문자 변환 · 불용어 제거 · 구두점 제거
    </text>

    <!-- Arrow 2 -->
    <line x1="500" y1="110" x2="580" y2="90" stroke="#64748b" stroke-width="2"/>
    <polygon points="580,90 570,87 573,97" fill="#64748b"/>

    <line x1="500" y1="150" x2="580" y2="170" stroke="#64748b" stroke-width="2"/>
    <polygon points="580,170 573,162 570,172" fill="#64748b"/>

    <!-- Vectorizers -->
    <rect x="580" y="50" width="220" height="70" rx="12" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="690" y="80" font-size="13" fill="#e0f2fe" text-anchor="middle">Bag-of-Words 벡터</text>

    <rect x="580" y="150" width="220" height="70" rx="12" fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="690" y="180" font-size="13" fill="#bbf7d0" text-anchor="middle">TF-IDF 벡터</text>
  </svg>
</div>

<!-- Preprocessing & Features -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
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
  <p>
    아래 도형은 피처 표현 방식과 분류 모델이 어떻게 조합되는지 요약한 구조도이다.
  </p>
</div>

<!-- Diagram 2 : Features & Models Map -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h3 style="margin-top:0;">Feature & Model Structure</h3>

  <svg width="100%" height="260" viewBox="0 0 840 260">
    <!-- Feature Block -->
    <rect x="60" y="70" width="220" height="120" rx="14" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="170" y="105" font-size="14" fill="#e5e7eb" text-anchor="middle">피처 표현</text>
    <text x="170" y="125" font-size="11" fill="#bae6fd" text-anchor="middle">Bag-of-Words</text>
    <text x="170" y="143" font-size="11" fill="#bae6fd" text-anchor="middle">TF-IDF</text>

    <!-- Arrows to classic models -->
    <line x1="280" y1="110" x2="360" y2="90" stroke="#64748b" stroke-width="2"/>
    <polygon points="360,90 350,87 353,97" fill="#64748b"/>

    <line x1="280" y1="140" x2="360" y2="140" stroke="#64748b" stroke-width="2"/>
    <polygon points="360,140 350,135 350,145" fill="#64748b"/>

    <!-- Logistic Regression -->
    <rect x="360" y="60" width="180" height="60" rx="12" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="450" y="95" font-size="13" fill="#e5e7eb" text-anchor="middle">Logistic Regression</text>

    <!-- SVM -->
    <rect x="360" y="120" width="180" height="60" rx="12" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="450" y="155" font-size="13" fill="#e5e7eb" text-anchor="middle">SVM</text>

    <!-- Arrow to RNN -->
    <line x1="280" y1="170" x2="360" y2="200" stroke="#64748b" stroke-width="2"/>
    <polygon points="360,200 353,192 350,202" fill="#64748b"/>

    <rect x="360" y="190" width="180" height="60" rx="12" fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="450" y="220" font-size="13" fill="#bbf7d0" text-anchor="middle">간단한 RNN 모델</text>

    <!-- Output -->
    <line x1="540" y1="90" x2="620" y2="130" stroke="#64748b" stroke-width="2"/>
    <polygon points="620,130 610,125 610,135" fill="#64748b"/>

    <line x1="540" y1="150" x2="620" y2="130" stroke="#64748b" stroke-width="2"/>

    <line x1="540" y1="220" x2="620" y2="130" stroke="#64748b" stroke-width="2"/>

    <rect x="620" y="100" width="170" height="60" rx="12" fill="#020617" stroke="#ec4899" stroke-width="2"/>
    <text x="705" y="130" font-size="13" fill="#f9a8d4" text-anchor="middle">긍정 / 부정 예측 결과</text>
  </svg>
</div>

<!-- Results & Discussion -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
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
  <p>
    아래 그래픽은 대표적인 두 모델(Logistic Regression vs RNN)에 대해
    Accuracy와 F1-score를 개념적으로 비교한 도표이다.
  </p>
</div>

<!-- Diagram 3 : Metrics Comparison -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h3 style="margin-top:0;">Accuracy & F1-score Comparison (개념도)</h3>

  <svg width="100%" height="230" viewBox="0 0 840 230">
    <!-- Axes -->
    <line x1="140" y1="180" x2="720" y2="180" stroke="#475569" stroke-width="1.5"/>
    <line x1="140" y1="60" x2="140" y2="180" stroke="#475569" stroke-width="1.5"/>

    <text x="130" y="60" font-size="11" fill="#9ca3af" text-anchor="end">Score</text>
    <text x="720" y="195" font-size="11" fill="#9ca3af" text-anchor="end">Model · Metric</text>

    <!-- Logistic Regression bars -->
    <rect x="200" y="110" width="40" height="70" fill="#6366f1"/>
    <rect x="250" y="120" width="40" height="60" fill="#22c55e"/>

    <text x="220" y="105" font-size="11" fill="#c7d2fe" text-anchor="middle">Acc</text>
    <text x="270" y="115" font-size="11" fill="#bbf7d0" text-anchor="middle">F1</text>
    <text x="235" y="190" font-size="11" fill="#e5e7eb" text-anchor="middle">LogReg</text>

    <!-- RNN bars -->
    <rect x="400" y="120" width="40" height="60" fill="#6366f1"/>
    <rect x="450" y="135" width="40" height="45" fill="#22c55e"/>

    <text x="420" y="115" font-size="11" fill="#c7d2fe" text-anchor="middle">Acc</text>
    <text x="470" y="130" font-size="11" fill="#bbf7d0" text-anchor="middle">F1</text>
    <text x="425" y="190" font-size="11" fill="#e5e7eb" text-anchor="middle">RNN</text>

    <!-- Legend -->
    <rect x="540" y="80" width="14" height="14" fill="#6366f1"/>
    <text x="560" y="91" font-size="11" fill="#c7d2fe">Accuracy(개념적)</text>

    <rect x="540" y="110" width="14" height="14" fill="#22c55e"/>
    <text x="560" y="121" font-size="11" fill="#bbf7d0">F1-score(개념적)</text>
  </svg>
</div>
