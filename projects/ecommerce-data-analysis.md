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

<!-- Overview -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Overview</h2>
  <p>
    온라인 쇼핑몰의 주문 이력 데이터를 바탕으로 고객별 구매 패턴을 분석하고,
    RFM(Recency, Frequency, Monetary) 지표를 이용해 고객을 여러 그룹으로 나누는 프로젝트다.
  </p>
  <p>
    아래 도형은 각 고객에 대해 어떤 정보를 추려내서 RFM 세 가지 지표로 요약했는지 간단히 보여준다.
  </p>
</div>

<!-- Diagram 1 : RFM 구조도 -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h3 style="margin-top:0;">RFM Metrics Diagram</h3>

  <svg width="100%" height="240" viewBox="0 0 820 240">
    <!-- 고객 주문 로그 -->
    <rect x="60" y="80" width="190" height="80" rx="12" fill="#020617" stroke="#f97316" stroke-width="2"/>
    <text x="155" y="115" font-size="14" fill="#e2e8f0" text-anchor="middle">주문 이력 데이터</text>
    <text x="155" y="135" font-size="11" fill="#fed7aa" text-anchor="middle">고객 ID / 주문일자 / 금액</text>

    <!-- 화살표 -->
    <line x1="250" y1="120" x2="320" y2="120" stroke="#64748b" stroke-width="2"/>
    <polygon points="320,120 310,115 310,125" fill="#64748b"/>

    <!-- RFM 박스 -->
    <rect x="320" y="40" width="180" height="60" rx="10" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="410" y="70" font-size="13" fill="#e2e8f0" text-anchor="middle">Recency</text>
    <text x="410" y="86" font-size="11" fill="#94a3b8" text-anchor="middle">마지막 구매 시점</text>

    <rect x="320" y="100" width="180" height="60" rx="10" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="410" y="130" font-size="13" fill="#e2e8f0" text-anchor="middle">Frequency</text>
    <text x="410" y="146" font-size="11" fill="#94a3b8" text-anchor="middle">구매 횟수</text>

    <rect x="320" y="160" width="180" height="60" rx="10" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="410" y="190" font-size="13" fill="#e2e8f0" text-anchor="middle">Monetary</text>
    <text x="410" y="206" font-size="11" fill="#94a3b8" text-anchor="middle">총 구매 금액</text>

    <!-- RFM → Segment -->
    <line x1="500" y1="120" x2="580" y2="120" stroke="#64748b" stroke-width="2"/>
    <polygon points="580,120 570,115 570,125" fill="#64748b"/>

    <rect x="580" y="80" width="180" height="80" rx="12" fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="670" y="115" font-size="14" fill="#bbf7d0" text-anchor="middle">고객 RFM 프로필</text>
    <text x="670" y="135" font-size="11" fill="#86efac" text-anchor="middle">점수 조합 → 등급 부여</text>
  </svg>
</div>

<!-- Data Processing -->
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
  <p>
    아래 플로우 도표는 원본 데이터에서 최종 고객 세그먼트가 만들어지는 흐름을 한 번에 정리한 것이다.
  </p>
</div>

<!-- Diagram 2 : Segmentation Flow -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h3 style="margin-top:0;">Customer Segmentation Flow</h3>

  <svg width="100%" height="260" viewBox="0 0 820 260">
    <!-- Step 1 -->
    <rect x="70" y="40" width="180" height="70" rx="12" fill="#020617" stroke="#f97316" stroke-width="2"/>
    <text x="160" y="70" font-size="13" fill="#e2e8f0" text-anchor="middle">원본 주문 데이터</text>
    <text x="160" y="88" font-size="11" fill="#fed7aa" text-anchor="middle">중복/결측 정리</text>

    <!-- Arrow -->
    <line x1="250" y1="75" x2="320" y2="75" stroke="#64748b" stroke-width="2"/>
    <polygon points="320,75 310,70 310,80" fill="#64748b"/>

    <!-- Step 2 -->
    <rect x="320" y="40" width="180" height="70" rx="12" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="410" y="70" font-size="13" fill="#e2e8f0" text-anchor="middle">고객별 집계</text>
    <text x="410" y="88" font-size="11" fill="#94a3b8" text-anchor="middle">Recency / F / M 계산</text>

    <!-- Arrow 2 -->
    <line x1="500" y1="75" x2="570" y2="75" stroke="#64748b" stroke-width="2"/>
    <polygon points="570,75 560,70 560,80" fill="#64748b"/>

    <!-- Step 3 -->
    <rect x="570" y="40" width="180" height="70" rx="12" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="660" y="70" font-size="13" fill="#e2e8f0" text-anchor="middle">RFM 스코어링</text>
    <text x="660" y="88" font-size="11" fill="#94a3b8" text-anchor="middle">구간별 점수 1~5 부여</text>

    <!-- Down Arrow -->
    <line x1="660" y1="110" x2="660" y2="150" stroke="#64748b" stroke-width="2"/>
    <polygon points="660,150 655,140 665,140" fill="#64748b"/>

    <!-- Step 4 -->
    <rect x="570" y="150" width="180" height="70" rx="12" fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="660" y="180" font-size="13" fill="#bbf7d0" text-anchor="middle">고객 세그먼트 라벨</text>
    <text x="660" y="198" font-size="11" fill="#86efac" text-anchor="middle">VIP / 충성 / 이탈위험 등</text>
  </svg>
</div>

<!-- Insights -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Insights</h2>
  <p>
    RFM 점수가 높은 소수의 고객이 전체 매출의 큰 부분을 차지하고 있다는 점,
    최근에 구매하지 않은 구간의 고객은 재방문 유도가 필요하다는 점 등을 데이터로 확인할 수 있었다.
    단순 통계 이상으로, “누구에게 어떤 마케팅을 해야 할지”에 대한 힌트를 얻게 된 프로젝트였다.
  </p>
  <p>
    아래 비교 그래픽은 대표적인 세 가지 고객 그룹의 상대적인 규모와 매출 기여도를 개념적으로 정리한 것이다.
  </p>
</div>

<!-- Diagram 3 : Segment Comparison -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h3 style="margin-top:0;">Customer Segment Comparison (개념도)</h3>

  <svg width="100%" height="230" viewBox="0 0 820 230">
    <!-- X/Y 축 -->
    <line x1="140" y1="180" x2="710" y2="180" stroke="#475569" stroke-width="1.5"/>
    <line x1="140" y1="60" x2="140" y2="180" stroke="#475569" stroke-width="1.5"/>

    <text x="130" y="60" font-size="11" fill="#94a3b8" text-anchor="end">매출 기여도</text>
    <text x="710" y="195" font-size="11" fill="#94a3b8" text-anchor="end">고객 수</text>

    <!-- Bars -->
    <!-- VIP -->
    <rect x="190" y="90" width="60" height="90" fill="#22c55e"/>
    <text x="220" y="85" font-size="11" fill="#bbf7d0" text-anchor="middle">VIP</text>

    <!-- Loyal -->
    <rect x="320" y="110" width="80" height="70" fill="#6366f1"/>
    <text x="360" y="105" font-size="11" fill="#c7d2fe" text-anchor="middle">충성 고객</text>

    <!-- Regular -->
    <rect x="470" y="135" width="90" height="45" fill="#38bdf8"/>
    <text x="515" y="130" font-size="11" fill="#e0f2fe" text-anchor="middle">일반 고객</text>

    <!-- At risk -->
    <rect x="630" y="150" width="60" height="30" fill="#f97316"/>
    <text x="660" y="145" font-size="11" fill="#fed7aa" text-anchor="middle">이탈 위험</text>

    <!-- Legend -->
    <rect x="160" y="40" width="14" height="14" fill="#22c55e"/>
    <text x="180" y="51" font-size="10" fill="#bbf7d0">매출 비중 높음</text>

    <rect x="280" y="40" width="14" height="14" fill="#6366f1"/>
    <text x="300" y="51" font-size="10" fill="#c7d2fe">빈번한 재구매</text>

    <rect x="420" y="40" width="14" height="14" fill="#38bdf8"/>
    <text x="440" y="51" font-size="10" fill="#e0f2fe">보통 수준</text>

    <rect x="550" y="40" width="14" height="14" fill="#f97316"/>
    <text x="570" y="51" font-size="10" fill="#fed7aa">이탈 관리 대상</text>
  </svg>
</div>
