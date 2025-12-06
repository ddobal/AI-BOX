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

<!-- Overview -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Overview</h2>
  <p>
    특정 버스 노선의 시간대별 승객 수 데이터를 바탕으로,
    앞으로의 승객 수를 예측하는 시계열 딥러닝 모델을 구현했다.
    간단한 회귀 모델과 LSTM 모델을 비교하는 것이 핵심 목표였다.
  </p>
  <p>
    아래 다이어그램은 시간축 위에서 승객 수가 어떻게 기록되고,
    그 뒤 구간을 예측 대상으로 잡았는지 시각적으로 나타낸 것이다.
  </p>
</div>

<!-- Diagram 1 : Time Series Input -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h3 style="margin-top:0;">Time Series Windowing</h3>
  <p style="margin-bottom:12px;">
    과거 일정 구간의 승객 수를 입력 윈도우로 사용하고, 바로 다음 구간의 승객 수를 예측하는 구조이다.
  </p>

  <svg width="100%" height="200" viewBox="0 0 820 200">
    <!-- Timeline -->
    <line x1="60" y1="120" x2="760" y2="120" stroke="#64748b" stroke-width="2"/>

    <!-- Past windows -->
    <rect x="80" y="80" width="140" height="60" rx="8" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="150" y="110" font-size="13" fill="#e2e8f0" text-anchor="middle">과거 t-3 ~ t-2</text>
    <text x="150" y="128" font-size="11" fill="#94a3b8" text-anchor="middle">승객 수</text>

    <rect x="250" y="80" width="140" height="60" rx="8" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="320" y="110" font-size="13" fill="#e2e8f0" text-anchor="middle">과거 t-2 ~ t-1</text>
    <text x="320" y="128" font-size="11" fill="#94a3b8" text-anchor="middle">승객 수</text>

    <rect x="420" y="80" width="140" height="60" rx="8" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="490" y="110" font-size="13" fill="#e2e8f0" text-anchor="middle">과거 t-1 ~ t</text>
    <text x="490" y="128" font-size="11" fill="#94a3b8" text-anchor="middle">승객 수</text>

    <!-- Arrow to prediction -->
    <line x1="560" y1="110" x2="650" y2="110" stroke="#64748b" stroke-width="2"/>
    <polygon points="650,110 640,105 640,115" fill="#64748b"/>

    <!-- Future -->
    <rect x="650" y="80" width="120" height="60" rx="8" fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="710" y="108" font-size="13" fill="#bbf7d0" text-anchor="middle">t+1 구간</text>
    <text x="710" y="126" font-size="11" fill="#86efac" text-anchor="middle">예측 승객 수</text>

    <!-- Labels -->
    <text x="140" y="170" font-size="11" fill="#94a3b8" text-anchor="middle">입력 윈도우 1</text>
    <text x="310" y="170" font-size="11" fill="#94a3b8" text-anchor="middle">입력 윈도우 2</text>
    <text x="480" y="170" font-size="11" fill="#94a3b8" text-anchor="middle">입력 윈도우 3</text>
  </svg>
</div>

<!-- Data & Model -->
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
  <p>
    아래 구조도는 입력 피처가 두 종류의 모델(기초 회귀 / LSTM)로 들어가는 전체 파이프라인을 보여준다.
  </p>
</div>

<!-- Diagram 2 : Model Pipeline -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h3 style="margin-top:0;">Model Pipeline</h3>

  <svg width="100%" height="260" viewBox="0 0 820 260">
    <!-- Input block -->
    <rect x="60" y="90" width="200" height="80" rx="12" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="160" y="120" font-size="14" fill="#e2e8f0" text-anchor="middle">입력 피처</text>
    <text x="160" y="140" font-size="11" fill="#94a3b8" text-anchor="middle">승객 수 / 요일 / 시간대 등</text>

    <!-- Split arrows -->
    <line x1="260" y1="120" x2="340" y2="70" stroke="#64748b" stroke-width="2"/>
    <polygon points="340,70 330,68 334,78" fill="#64748b"/>
    <line x1="260" y1="140" x2="340" y2="190" stroke="#64748b" stroke-width="2"/>
    <polygon points="340,190 334,182 330,192" fill="#64748b"/>

    <!-- Baseline model -->
    <rect x="340" y="40" width="200" height="70" rx="12" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="440" y="70" font-size="14" fill="#e2e8f0" text-anchor="middle">기초 회귀 / ARIMA</text>
    <text x="440" y="88" font-size="11" fill="#94a3b8" text-anchor="middle">전통 시계열 모델</text>

    <!-- LSTM model -->
    <rect x="340" y="170" width="200" height="70" rx="12" fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="440" y="200" font-size="14" fill="#bbf7d0" text-anchor="middle">LSTM 네트워크</text>
    <text x="440" y="218" font-size="11" fill="#86efac" text-anchor="middle">순서 정보 학습</text>

    <!-- Arrows to output -->
    <line x1="540" y1="75" x2="630" y2="75" stroke="#64748b" stroke-width="2"/>
    <polygon points="630,75 620,70 620,80" fill="#64748b"/>

    <line x1="540" y1="205" x2="630" y2="205" stroke="#64748b" stroke-width="2"/>
    <polygon points="630,205 620,200 620,210" fill="#64748b"/>

    <!-- Output blocks -->
    <rect x="630" y="50" width="140" height="50" rx="10" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="700" y="75" font-size="12" fill="#e2e8f0" text-anchor="middle">기초 모델 예측</text>

    <rect x="630" y="180" width="140" height="50" rx="10" fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="700" y="205" font-size="12" fill="#bbf7d0" text-anchor="middle">LSTM 예측</text>
  </svg>
</div>

<!-- Results & Takeaways -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Results & Takeaways</h2>
  <p>
    단기 예측에서는 전통적인 회귀 모델과 LSTM의 성능 차이가 크지 않았지만,
    패턴이 복잡한 구간에서는 LSTM이 조금 더 나은 결과를 보여주었다.
    시계열 데이터에서 “순서 정보”를 어떻게 다루느냐가 중요한 포인트라는 것을 알게 되었다.
  </p>
  <p>
    아래 비교 도형은 두 모델의 평균 RMSE를 단순화해 표현한 것이며,
    구체적인 값보다는 “상대적인 경향”을 보여주는 데 초점을 두었다.
  </p>
</div>

<!-- Diagram 3 : RMSE Comparison -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h3 style="margin-top:0;">RMSE Comparison (개념도)</h3>

  <svg width="100%" height="220" viewBox="0 0 820 220">
    <!-- Axis -->
    <line x1="140" y1="170" x2="700" y2="170" stroke="#475569" stroke-width="1.5"/>
    <line x1="140" y1="60" x2="140" y2="170" stroke="#475569" stroke-width="1.5"/>

    <text x="140" y="50" font-size="11" fill="#94a3b8" text-anchor="middle">오차(RMSE)</text>
    <text x="230" y="190" font-size="11" fill="#94a3b8" text-anchor="middle">Baseline</text>
    <text x="420" y="190" font-size="11" fill="#94a3b8" text-anchor="middle">LSTM</text>

    <!-- Bars -->
    <rect x="210" y="100" width="40" height="70" fill="#6366f1"/>
    <rect x="400" y="120" width="40" height="50" fill="#22c55e"/>

    <!-- Labels -->
    <text x="230" y="95" font-size="11" fill="#c7d2fe" text-anchor="middle">RMSE 높음</text>
    <text x="420" y="115" font-size="11" fill="#bbf7d0" text-anchor="middle">RMSE 조금↓</text>

    <!-- Legend -->
    <rect x="540" y="80" width="16" height="16" fill="#6366f1"/>
    <text x="565" y="92" font-size="11" fill="#cbd5f5">기초 회귀·ARIMA</text>

    <rect x="540" y="110" width="16" height="16" fill="#22c55e"/>
    <text x="565" y="122" font-size="11" fill="#bbf7d0">LSTM 모델</text>
  </svg>
</div>
