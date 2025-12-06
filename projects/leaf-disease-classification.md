---
layout: project
title: 식물 잎 병해 이미지 분류
permalink: /projects/leaf-disease-classification/
order: 3
---

<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 잎사귀 아이콘 -->
    <svg viewBox="0 0 24 24" width="32" height="32">
      <path d="M5 19C5 8 12 4 19 5c-1 7-5 14-14 14z" fill="url(#leafGrad)"/>
      <defs>
        <linearGradient id="leafGrad" x1="0" y1="0" x2="1" y2="1">
          <stop offset="0%" stop-color="#22c55e"/>
          <stop offset="100%" stop-color="#16a34a"/>
        </linearGradient>
      </defs>
    </svg>
  </div>

  <h1>식물 잎 병해 이미지 분류</h1>
  <p class="mini-hero-sub">
    농업 분야 데이터셋을 활용해 건강한 잎과 병든 잎을 구분하는 컴퓨터비전 프로젝트
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h2>Overview</h2>
  <p>
    PlantVillage와 유사한 잎 사진 데이터셋을 이용해,
    잎이 건강한 상태인지 특정 병해에 감염된 상태인지를 분류하는 모델을 구현했다.
    실제 산업 적용 가능성을 염두에 두고, 간단하지만 의미 있는 문제를 선택했다.
  </p>
  <p>
    아래 흐름도는 원본 이미지가 어떻게 전처리되고,
    어떤 모델에 입력되는지 전체 구조를 요약한 것이다.
  </p>
</div>

<!-- Diagram 1 : Full Pipeline -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h3 style="margin-top:0;">Image Classification Pipeline</h3>

  <svg width="100%" height="260" viewBox="0 0 860 260">
    <!-- Raw Dataset -->
    <rect x="40" y="90" width="180" height="70" rx="12" fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="130" y="120" font-size="14" fill="#e2e8f0" text-anchor="middle">원본 잎 이미지</text>
    <text x="130" y="140" font-size="11" fill="#86efac" text-anchor="middle">Healthy / Diseased</text>

    <!-- Arrow -->
    <line x1="220" y1="125" x2="300" y2="125" stroke="#64748b" stroke-width="2"/>
    <polygon points="300,125 290,120 290,130" fill="#64748b"/>

    <!-- Augmentation -->
    <rect x="300" y="70" width="200" height="110" rx="12" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="400" y="105" font-size="14" fill="#e2e8f0" text-anchor="middle">데이터 증강</text>
    <text x="400" y="125" font-size="11" fill="#94a3b8" text-anchor="middle">Rotation / Flip / Color Jitter</text>

    <!-- Split arrows -->
    <line x1="500" y1="100" x2="580" y2="60" stroke="#64748b" stroke-width="2"/>
    <polygon points="580,60 570,58 574,68" fill="#64748b"/>

    <line x1="500" y1="150" x2="580" y2="190" stroke="#64748b" stroke-width="2"/>
    <polygon points="580,190 574,182 570,192" fill="#64748b"/>

    <!-- CNN Model -->
    <rect x="580" y="20" width="220" height="80" rx="14" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="690" y="55" font-size="14" fill="#e2e8f0" text-anchor="middle">기본 CNN 모델</text>
    <text x="690" y="73" font-size="11" fill="#c7d2fe" text-anchor="middle">Conv → Pool → FC</text>

    <!-- ResNet Model -->
    <rect x="580" y="160" width="220" height="80" rx="14" fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="690" y="195" font-size="14" fill="#bbf7d0" text-anchor="middle">전이학습: ResNet</text>
    <text x="690" y="213" font-size="11" fill="#86efac" text-anchor="middle">Feature Extractor + Classifier</text>
  </svg>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h2>Model & Training</h2>
  <p>
    기본 CNN 모델과 사전 학습된(pretrained) ResNet 계열 모델을 비교해보는 방식으로 진행했다.
    데이터 수가 많지 않은 경우에는 전이학습(transfer learning)이 훨씬 유리하다는 점을 직접 확인할 수 있었다.
  </p>
  <p>
    아래 도형은 내가 구성한 기본 CNN 모델을 시각적으로 표현한 개념도이다.
  </p>
</div>

<!-- Diagram 2 : CNN Architecture -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h3 style="margin-top:0;">Basic CNN Architecture</h3>

  <svg width="100%" height="240" viewBox="0 0 860 240">
    <!-- Input -->
    <rect x="60" y="90" width="120" height="60" rx="10" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="120" y="120" font-size="13" fill="#e2e8f0" text-anchor="middle">입력 이미지</text>

    <!-- Conv1 -->
    <line x1="180" y1="120" x2="250" y2="120" stroke="#64748b" stroke-width="2"/>
    <polygon points="250,120 240,115 240,125" fill="#64748b"/>
    <rect x="250" y="90" width="130" height="60" rx="10" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="315" y="120" fill="#e2e8f0" font-size="13" text-anchor="middle">Conv + ReLU</text>

    <!-- Pool -->
    <line x1="380" y1="120" x2="460" y2="120" stroke="#64748b" stroke-width="2"/>
    <polygon points="460,120 450,115 450,125" fill="#64748b"/>
    <rect x="460" y="90" width="130" height="60" rx="10" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="525" y="120" fill="#e2e8f0" font-size="13" text-anchor="middle">MaxPooling</text>

    <!-- FC -->
    <line x1="590" y1="120" x2="660" y2="120" stroke="#64748b" stroke-width="2"/>
    <polygon points="660,120 650,115 650,125" fill="#64748b"/>
    <rect x="660" y="90" width="150" height="60" rx="10" fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="735" y="120" fill="#e2e8f0" font-size="13" text-anchor="middle">Fully Connected</text>
  </svg>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h2>What I Learned</h2>
  <p>
    현실 세계 이미지는 MNIST처럼 깨끗하지 않아서, 전처리와 데이터 증강의 중요성이 크다는 점을 느꼈다.
    또한, 단순히 정확도만 보는 것이 아니라 클래스별 혼동행렬을 통해
    어떤 클래스에서 실수가 많이 나는지도 함께 분석하는 습관을 갖게 되었다.
  </p>
  <p>
    마지막 도형은 기본 CNN과 ResNet 전이학습의 정확도를 비교한 개념적 그래픽이다.
  </p>
</div>

<!-- Diagram 3 : Accuracy Comparison -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h3 style="margin-top:0;">Accuracy Comparison (개념도)</h3>

  <svg width="100%" height="220" viewBox="0 0 860 220">
    <!-- Axis -->
    <line x1="140" y1="170" x2="760" y2="170" stroke="#475569" stroke-width="1.5"/>
    <line x1="140" y1="70" x2="140" y2="170" stroke="#475569" stroke-width="1.5"/>

    <text x="130" y="65" font-size="11" fill="#94a3b8" text-anchor="end">정확도</text>
    <text x="760" y="190" font-size="11" fill="#94a3b8" text-anchor="end">모델</text>

    <!-- Bars -->
    <rect x="260" y="120" width="90" height="50" fill="#38bdf8"/>
    <text x="305" y="115" font-size="12" fill="#e0f2fe" text-anchor="middle">CNN</text>

    <rect x="460" y="90" width="90" height="80" fill="#22c55e"/>
    <text x="505" y="85" font-size="12" fill="#bbf7d0" text-anchor="middle">ResNet</text>

    <!-- Labels -->
    <text x="305" y="115" fill="#e0f2fe" font-size="11" text-anchor="middle">기본 정확도</text>
    <text x="505" y="85" fill="#bbf7d0" font-size="11" text-anchor="middle">더 높은 정확도</text>

    <!-- Legend -->
    <rect x="630" y="80" width="14" height="14" fill="#38bdf8"/>
    <text x="650" y="91" font-size="11" fill="#e0f2fe">Baseline CNN</text>

    <rect x="630" y="110" width="14" height="14" fill="#22c55e"/>
    <text x="650" y="121" font-size="11" fill="#bbf7d0">ResNet Transfer</text>
  </svg>
</div>
