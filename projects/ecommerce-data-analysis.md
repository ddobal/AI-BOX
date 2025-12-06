---
layout: project
title: 온라인 쇼핑몰 고객 데이터 분석
permalink: /projects/ecommerce-data-analysis/
order: 6
---

<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 쇼핑 카트 아이콘 -->
    <svg viewBox="0 0 24 24" width="32" height="32">
      <path d="M4 5h2l2 11h10l2-7H9" stroke="#f97316" stroke-width="1.6" fill="none"/>
      <circle cx="10" cy="19" r="1.4" fill="#f97316"/>
      <circle cx="17" cy="19" r="1.4" fill="#f97316"/>
    </svg>
  </div>

  <h1>온라인 쇼핑몰 고객 데이터 분석</h1>
  <p class="mini-hero-sub">
    RFM 분석과 간단한 시각화를 통해 고객 유형을 분류해 본 데이터 분석 프로젝트
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Overview</h2>
  <p>
    온라인 쇼핑몰의 주문 이력 데이터를 바탕으로 고객별 구매 패턴을 분석하고,
    RFM(Recency, Frequency, Monetary) 지표를 이용해 고객을 여러 그룹으로 나누는 프로젝트다.
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Data Processing</h2>
  <p>
    주문 날짜, 구매 금액, 고객 ID를 중심으로 데이터를 정리하고,
    고객별로 최근 구매일, 구매 횟수, 총 구매액을 계산했다.
    이후 각 지표를 구간별로 나누어 점수를 부여하고, 점수 조합에 따라 고객 등급을 나누었다.
  </p>
  <p>
    Python의 pandas와 matplotlib/seaborn을 사용해
    각 그룹의 분포를 시각화하고 특징을 비교했다.
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Insights</h2>
  <p>
    RFM 점수가 높은 소수의 고객이 전체 매출의 큰 부분을 차지하고 있다는 점,
    최근에 구매하지 않은 구간의 고객은 재방문 유도가 필요하다는 점 등을 데이터로 확인할 수 있었다.
    단순 통계 이상으로, “누구에게 어떤 마케팅을 해야 할지”에 대한 힌트를 얻게 된 프로젝트였다.
  </p>
</div>
