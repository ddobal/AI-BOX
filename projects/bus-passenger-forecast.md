---
layout: project
title: 대중교통 승객 수 예측
permalink: /projects/bus-passenger-forecast/
order: 4
---

<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 그래프 아이콘 -->
    <svg viewBox="0 0 24 24" width="32" height="32">
      <path d="M4 19V5" stroke="#38bdf8" stroke-width="1.6"/>
      <path d="M5 15l4-6 4 4 6-8" stroke="#22c55e" stroke-width="1.6" fill="none"/>
    </svg>
  </div>

  <h1>대중교통 승객 수 예측</h1>
  <p class="mini-hero-sub">
    시간에 따른 승객 수 변화를 LSTM 기반으로 예측해 본 시계열 분석 프로젝트
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Overview</h2>
  <p>
    특정 버스 노선의 시간대별 승객 수 데이터를 바탕으로,
    앞으로의 승객 수를 예측하는 시계열 딥러닝 모델을 구현했다.
    간단한 회귀 모델과 LSTM 모델을 비교하는 것이 핵심 목표였다.
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Data & Model</h2>
  <p>
    데이터는 시간 순서대로 정렬된 승객 수 기록이며, 요일·시간대 등의 정보를 함께 피처로 사용했다.
    먼저 이동평균과 ARIMA 같은 전통적인 시계열 기법을 시도한 뒤,
    LSTM 네트워크를 사용해 더 복잡한 패턴을 학습하도록 했다.
  </p>
  <p>
    손실 함수는 MSE를 사용했고, 예측 성능 평가는 RMSE와 MAE로 확인했다.
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Results & Takeaways</h2>
  <p>
    단기 예측에서는 전통적인 회귀 모델과 LSTM의 성능 차이가 크지 않았지만,
    패턴이 복잡한 구간에서는 LSTM이 조금 더 나은 결과를 보여주었다.
    시계열 데이터에서 “순서 정보”를 어떻게 다루느냐가 중요한 포인트라는 것을 알게 되었다.
  </p>
</div>
