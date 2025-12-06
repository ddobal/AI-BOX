---
layout: post
title: "Train / Validation / Test 분할과 과적합 체험기"
date: 2025-03-25
tags: [machine-learning, overfitting, data-split]
excerpt: "다항 회귀 실험을 통해 train·validation·test 분할과 과적합 패턴이 실제로 어떻게 보이는지 직접 확인한 기록."
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
  <svg viewBox="0 0 24 24" fill="none">
    <path d="M4 19V5" stroke="#38bdf8" stroke-width="1.6"/>
    <path d="M5 15l4-4 4 3 6-7" stroke="#38bdf8" stroke-width="1.6" fill="none"/>
  </svg>
  <h2>실험 목적</h2>
</div>

<p>
  수업에서 항상 등장하는 train / validation / test 분할이
  실제 모델 성능에 어떤 영향을 주는지 직접 확인해보고 싶었다.
  특히 과적합(overfitting)을 일부러 만들어 보고,
  손실 곡선에서 그 패턴이 어떻게 보이는지 관찰하는 것이 목표였다.
</p>

<div class="post-section-title">
  <svg viewBox="0 0 24 24" fill="none">
    <rect x="4" y="4" width="16" height="16" rx="2" stroke="#a855f7" stroke-width="1.5"/>
    <path d="M8 10h8M8 14h5" stroke="#a855f7" stroke-width="1.5" stroke-linecap="round"/>
  </svg>
  <h2>실험 구성</h2>
</div>

<p>
  데이터는 회귀용 예제 데이터(`make_regression`)를 사용했고,
  60%/20%/20% 비율로 train/validation/test를 나눴다.
  모델은 다항 회귀(Polynomial Regression)를 사용했고,
  차수를 1, 3, 5, 9차로 바꿔가며 비교했다.
</p>
<p>
  각 설정마다 train/validation loss를 기록하고,
  최종 성능은 test셋에서만 평가했다.
</p>

<div class="post-section-title">
  <svg viewBox="0 0 24 24" fill="none">
    <circle cx="12" cy="12" r="9" stroke="#22c55e" stroke-width="1.5"/>
    <path d="M9 13l2 2 4-5" stroke="#22c55e" stroke-width="1.5" stroke-linecap="round" />
  </svg>
  <h2>관찰 내용</h2>
</div>

<p>
  1차, 3차 모델은 train과 validation loss가 비슷하게 감소하면서
  비교적 안정적인 곡선을 보였다.
  반대로 9차 모델은 train loss는 거의 0에 가깝게 떨어지는데,
  validation loss는 어느 순간부터 다시 올라가는 전형적인 과적합 패턴이 나타났다.
</p>
<p>
  validation 기준으로 가장 좋은 모델을 고르면
  항상 가장 복잡한 모델이 아니라는 점이 확실하게 눈에 들어왔다.
</p>

<div class="post-section-title">
  <svg viewBox="0 0 24 24" fill="none">
    <rect x="5" y="4" width="14" height="16" rx="2" stroke="#e5e7eb" stroke-width="1.4"/>
    <path d="M8 9h8M8 13h6" stroke="#e5e7eb" stroke-width="1.4" stroke-linecap="round"/>
  </svg>
  <h2>느낀 점</h2>
</div>

<p>
  “과적합은 나쁘다”라는 말만 듣고 넘기기 쉬운데,
  그래프를 직접 그려보니 왜 validation 셋을 따로 두는지 훨씬 잘 이해할 수 있었다.
  앞으로는 단순히 train 성능만 올리는 것이 아니라,
  일반화가 잘 되는 모델을 선택하는 연습을 더 많이 해 봐야겠다.
</p>
