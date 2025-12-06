---
layout: post
title: "기초 분류 모델 비교: 로지스틱 회귀 vs KNN"
date: 2025-12-01
tags: [machine-learning, classification, practice]
excerpt: "기초 분류 알고리즘인 로지스틱 회귀와 KNN을 같은 데이터셋에 적용해 성능과 특징을 비교한 실험 기록."
---

<style>
  .post-section-title {
    display: flex;
    align-items: center;
    gap: 8px;
    margin: 20px 0 10px;
  }
  .post-section-title svg {
    width: 20px;
    height: 20px;
  }
</style>

<div class="post-section-title">
  <!-- 목표 아이콘 -->
  <svg viewBox="0 0 24 24" fill="none">
    <circle cx="12" cy="12" r="9" stroke="#38bdf8" stroke-width="1.5"/>
    <circle cx="12" cy="12" r="4" stroke="#38bdf8" stroke-width="1.5"/>
    <path d="M12 8v4l2 2" stroke="#38bdf8" stroke-width="1.5" stroke-linecap="round" />
  </svg>
  <h2>실험 목적</h2>
</div>

<p>
  이번 실험의 목표는 기초 분류 모델인 로지스틱 회귀와 K-최근접 이웃(KNN)을 직접 돌려보고,
  둘의 성능과 특성을 비교해보는 것이다. 이론상으로만 알고 있던 내용을
  실제 데이터에 적용해보면서 감을 잡는 데 초점을 뒀다.
  사용한 데이터는 사이킷런에서 제공하는 간단한 이진 분류용 예제 데이터(예: breast cancer 데이터셋)를 활용했다.
</p>

<div class="post-section-title">
  <!-- 설정 아이콘 -->
  <svg viewBox="0 0 24 24" fill="none">
    <circle cx="12" cy="12" r="3" stroke="#a855f7" stroke-width="1.5"/>
    <path d="M4 12h2.2M17.8 12H20M7.1 7.1l1.6 1.6M15.3 15.3l1.6 1.6M7.1 16.9l1.6-1.6M15.3 8.7l1.6-1.6"
          stroke="#a855f7" stroke-width="1.5" stroke-linecap="round"/>
  </svg>
  <h2>실험 설정</h2>
</div>

<p>
  사용 데이터는 scikit-learn 내장 이진 분류 데이터셋이고, train 70%, test 30%로 분할했다.
  입력 피처는 StandardScaler로 정규화했다.
</p>
<p>
  비교한 모델은 다음과 같다.
</p>
<ul>
  <li>Logistic Regression (L2 정규화, 기본 설정)</li>
  <li>KNN (k = 3, 5, 7 세 가지)</li>
</ul>
<p>
  성능 평가는 Accuracy와 F1-score를 함께 확인했다.
</p>

<div class="post-section-title">
  <!-- 결과 아이콘 -->
  <svg viewBox="0 0 24 24" fill="none">
    <path d="M4 19V5" stroke="#22c55e" stroke-width="1.6"/>
    <path d="M5 15l4-4 4 3 6-7" stroke="#22c55e" stroke-width="1.6" fill="none"/>
  </svg>
  <h2>결과 요약</h2>
</div>

<p>
  로지스틱 회귀는 전체적으로 안정적인 성능을 보였고, 과적합 느낌은 거의 없었다.
  KNN은 k=3일 때 훈련 데이터에 더 잘 맞지만 test 성능이 살짝 떨어지는 경향이 있었고,
  k가 커질수록 결정 경계가 부드러워지는 느낌이었다.
</p>
<p>
  테스트셋 기준으로는 로지스틱 회귀와 KNN(k=5)의 정확도가 비슷하게 나왔고,
  데이터가 그리 복잡하지 않아서 단순한 모델도 충분히 잘 작동한다는 걸 확인했다.
</p>

<div class="post-section-title">
  <!-- 메모 아이콘 -->
  <svg viewBox="0 0 24 24" fill="none">
    <rect x="5" y="4" width="14" height="16" rx="2" stroke="#e5e7eb" stroke-width="1.4"/>
    <path d="M8 9h8M8 13h5" stroke="#e5e7eb" stroke-width="1.4" stroke-linecap="round"/>
  </svg>
  <h2>느낀 점</h2>
</div>

<p>
  앞으로 복잡한 딥러닝 모델로 넘어가기 전에,
  이런 기초 분류 모델들만으로도 꽤 많은 문제를 풀 수 있다는 걸 다시 확인했다.
  성능이 비슷하다면 해석이 쉬운 모델(로지스틱 회귀)을 선택하는 것도 중요한 전략이라는 생각이 들었다.
</p>
