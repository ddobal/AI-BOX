---
layout: project
title: MNIST 손글씨 숫자 분류
permalink: /projects/mnist-digit-classification/
order: 1
---

<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 숫자/딥러닝 느낌 아이콘 -->
    <svg viewBox="0 0 24 24" width="32" height="32">
      <rect x="3" y="3" width="18" height="18" rx="3" fill="url(#mnistGrad)"/>
      <text x="8" y="16" font-size="9" fill="#0b1120">0~9</text>
      <defs>
        <linearGradient id="mnistGrad" x1="0" y1="0" x2="1" y2="1">
          <stop offset="0%" stop-color="#4f46e5"/>
          <stop offset="100%" stop-color="#22c55e"/>
        </linearGradient>
      </defs>
    </svg>
  </div>

  <h1>MNIST 손글씨 숫자 분류</h1>
  <p class="mini-hero-sub">
    딥러닝 기초에서 가장 많이 사용하는 MNIST 데이터셋으로 CNN 분류 모델을 구현한 프로젝트
  </p>
</div>

<!-- Overview -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h2>Overview</h2>
  <p>
    이 프로젝트는 딥러닝 입문 단계에서 가장 기본이 되는 MNIST 손글씨 숫자 데이터셋을 이용해
    간단한 합성곱 신경망(CNN) 분류기를 구현해보는 것을 목표로 한다.
    28×28 흑백 이미지를 입력으로 받아 0~9까지의 숫자 클래스를 예측한다.
  </p>
  <p>
    처음에는 완전연결 신경망(MLP)로 시작해서, 이후 CNN 구조로 바꾸었을 때
    정확도가 어떻게 달라지는지 비교해보는 과정도 함께 진행했다.
  </p>
  <p>
    아래 도형은 MNIST 데이터셋의 일부 예시 이미지를 개념적으로 표현한 것이다.
  </p>
</div>

<!-- Diagram 1: MNIST Sample Grid -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h3 style="margin-top:0;">MNIST Sample Digits (개념도)</h3>

  <svg width="100%" height="220" viewBox="0 0 820 220">
    <!-- 4x5 grid of squares with digits -->
    <!-- Row 1 -->
    <rect x="80" y="40" width="60" height="60" rx="6" fill="#020617" stroke="#4f46e5" stroke-width="1.5"/>
    <text x="110" y="78" font-size="22" fill="#e5e7eb" text-anchor="middle">0</text>

    <rect x="160" y="40" width="60" height="60" rx="6" fill="#020617" stroke="#4f46e5" stroke-width="1.5"/>
    <text x="190" y="78" font-size="22" fill="#e5e7eb" text-anchor="middle">1</text>

    <rect x="240" y="40" width="60" height="60" rx="6" fill="#020617" stroke="#4f46e5" stroke-width="1.5"/>
    <text x="270" y="78" font-size="22" fill="#e5e7eb" text-anchor="middle">2</text>

    <rect x="320" y="40" width="60" height="60" rx="6" fill="#020617" stroke="#4f46e5" stroke-width="1.5"/>
    <text x="350" y="78" font-size="22" fill="#e5e7eb" text-anchor="middle">3</text>

    <rect x="400" y="40" width="60" height="60" rx="6" fill="#020617" stroke="#4f46e5" stroke-width="1.5"/>
    <text x="430" y="78" font-size="22" fill="#e5e7eb" text-anchor="middle">4</text>

    <!-- Row 2 -->
    <rect x="80" y="120" width="60" height="60" rx="6" fill="#020617" stroke="#22c55e" stroke-width="1.5"/>
    <text x="110" y="158" font-size="22" fill="#bbf7d0" text-anchor="middle">5</text>

    <rect x="160" y="120" width="60" height="60" rx="6" fill="#020617" stroke="#22c55e" stroke-width="1.5"/>
    <text x="190" y="158" font-size="22" fill="#bbf7d0" text-anchor="middle">6</text>

    <rect x="240" y="120" width="60" height="60" rx="6" fill="#020617" stroke="#22c55e" stroke-width="1.5"/>
    <text x="270" y="158" font-size="22" fill="#bbf7d0" text-anchor="middle">7</text>

    <rect x="320" y="120" width="60" height="60" rx="6" fill="#020617" stroke="#22c55e" stroke-width="1.5"/>
    <text x="350" y="158" font-size="22" fill="#bbf7d0" text-anchor="middle">8</text>

    <rect x="400" y="120" width="60" height="60" rx="6" fill="#020617" stroke="#22c55e" stroke-width="1.5"/>
    <text x="430" y="158" font-size="22" fill="#bbf7d0" text-anchor="middle">9</text>

    <!-- Caption -->
    <text x="600" y="110" font-size="13" fill="#e5e7eb">28×28 흑백 손글씨 이미지</text>
    <text x="600" y="130" font-size="11" fill="#9ca3af">각 픽셀 값(0~255) → 정규화 후 모델 입력</text>
  </svg>
</div>

<!-- Dataset & Methods -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h2>Dataset & Methods</h2>
  <p>
    사용한 데이터셋은 유명한 MNIST 손글씨 이미지(60,000개 학습, 10,000개 테스트)이며,
    PyTorch 또는 TensorFlow의 내장 모듈을 통해 손쉽게 로드했다.
    전처리는 픽셀 값 정규화와 간단한 augmentation(랜덤 시프트, 회전) 정도만 적용했다.
  </p>
  <p>
    모델 구조는 Conv2D → ReLU → MaxPool을 두 번 반복하고,
    이후 Flatten 후 Dense 레이어를 거쳐 softmax로 출력하는 전형적인 CNN 구조를 사용했다.
    손실함수는 cross entropy, 최적화는 Adam 옵티마이저를 사용했다.
  </p>
  <p>
    아래 도식은 프로젝트에서 사용한 기본 CNN 구조를 한눈에 볼 수 있게 정리한 것이다.
  </p>
</div>

<!-- Diagram 2: CNN Architecture -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h3 style="margin-top:0;">CNN Architecture Diagram</h3>

  <svg width="100%" height="260" viewBox="0 0 840 260">
    <!-- Input -->
    <rect x="40" y="100" width="130" height="70" rx="10" fill="#020617" stroke="#4f46e5" stroke-width="2"/>
    <text x="105" y="130" font-size="13" fill="#e5e7eb" text-anchor="middle">28×28 입력</text>
    <text x="105" y="148" font-size="11" fill="#9ca3af" text-anchor="middle">1 채널(흑백)</text>

    <!-- Arrow 1 -->
    <line x1="170" y1="135" x2="230" y2="135" stroke="#64748b" stroke-width="2"/>
    <polygon points="230,135 220,130 220,140" fill="#64748b"/>

    <!-- Conv + ReLU 1 -->
    <rect x="230" y="80" width="150" height="110" rx="12" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="305" y="115" font-size="13" fill="#e5e7eb" text-anchor="middle">Conv2D(32)</text>
    <text x="305" y="133" font-size="11" fill="#c7d2fe" text-anchor="middle">3×3 kernel + ReLU</text>

    <!-- Arrow 2 -->
    <line x1="380" y1="135" x2="440" y2="135" stroke="#64748b" stroke-width="2"/>
    <polygon points="440,135 430,130 430,140" fill="#64748b"/>

    <!-- Conv + ReLU 2 + Pool -->
    <rect x="440" y="70" width="170" height="130" rx="12" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="525" y="105" font-size="13" fill="#e5e7eb" text-anchor="middle">Conv2D(64) + ReLU</text>
    <text x="525" y="125" font-size="11" fill="#bae6fd" text-anchor="middle">3×3 kernel</text>
    <text x="525" y="145" font-size="11" fill="#bae6fd" text-anchor="middle">MaxPool(2×2)</text>

    <!-- Arrow 3 -->
    <line x1="610" y1="135" x2="670" y2="135" stroke="#64748b" stroke-width="2"/>
    <polygon points="670,135 660,130 660,140" fill="#64748b"/>

    <!-- FC -->
    <rect x="670" y="90" width="140" height="90" rx="12" fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="740" y="120" font-size="13" fill="#e5e7eb" text-anchor="middle">FC + Softmax</text>
    <text x="740" y="140" font-size="11" fill="#bbf7d0" text-anchor="middle">출력: 10 클래스</text>
  </svg>
</div>

<!-- Experiments -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h2>Experiments</h2>
  <p>
    에폭 수, 배치 크기, 학습률(learning rate)을 바꿔가며 실험해 보았고,
    과적합 여부를 보기 위해 train/validation loss 곡선도 함께 기록했다.
    기본 설정에서는 약 98% 정도의 테스트 정확도가 나와
    교과서적인 결과에 가까운 성능을 확인했다.
  </p>
  <p>
    또 학습이 잘 안 되는 경우(학습률이 너무 크거나 너무 작은 경우)도 일부러 만들어 보고,
    그래프가 어떻게 달라지는지 관찰하여 하이퍼파라미터의 중요성을 체감했다.
  </p>
  <p>
    아래 그래프는 정상적인 학습 설정과, 학습률이 잘못 설정된 경우의 손실 곡선을 개념적으로 비교한 것이다.
  </p>
</div>

<!-- Diagram 3: Training vs Validation Loss -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h3 style="margin-top:0;">Train / Validation Loss (개념도)</h3>

  <svg width="100%" height="260" viewBox="0 0 840 260">
    <!-- Axes -->
    <line x1="120" y1="200" x2="720" y2="200" stroke="#475569" stroke-width="1.5"/>
    <line x1="120" y1="50" x2="120" y2="200" stroke="#475569" stroke-width="1.5"/>

    <text x="110" y="50" font-size="11" fill="#9ca3af" text-anchor="end">Loss</text>
    <text x="720" y="215" font-size="11" fill="#9ca3af" text-anchor="end">Epoch</text>

    <!-- Good setting: train/val both decreasing and close -->
    <path d="M 130 90 C 220 120, 310 145, 400 160" stroke="#22c55e" stroke-width="2" fill="none"/>
    <path d="M 130 100 C 220 130, 310 150, 400 165" stroke="#a3e635" stroke-width="2" fill="none" stroke-dasharray="4 4"/>

    <!-- Bad setting: very noisy / not decreasing -->
    <path d="M 430 140 C 520 130, 610 135, 700 130" stroke="#ef4444" stroke-width="2" fill="none"/>
    <path d="M 430 150 C 520 155, 610 150, 700 155" stroke="#f97316" stroke-width="2" fill="none" stroke-dasharray="4 4"/>

    <!-- Labels -->
    <text x="250" y="80" font-size="11" fill="#bbf7d0">적절한 학습률: 손실이 안정적으로 감소</text>
    <text x="555" y="120" font-size="11" fill="#fecaca" text-anchor="middle">잘못된 학습률: 손실이 불안정하거나 감소하지 않음</text>

    <!-- Legend -->
    <rect x="140" y="210" width="14" height="14" fill="none" stroke="#22c55e" stroke-width="2"/>
    <text x="160" y="221" font-size="11" fill="#bbf7d0">Train (Good)</text>

    <rect x="250" y="210" width="14" height="14" fill="none" stroke="#a3e635" stroke-width="2"/>
    <text x="270" y="221" font-size="11" fill="#d9f99d">Val (Good)</text>

    <rect x="360" y="210" width="14" height="14" fill="none" stroke="#ef4444" stroke-width="2"/>
    <text x="380" y="221" font-size="11" fill="#fecaca">Train (Bad)</text>

    <rect x="470" y="210" width="14" height="14" fill="none" stroke="#f97316" stroke-width="2"/>
    <text x="490" y="221" font-size="11" fill="#fed7aa">Val (Bad)</text>
  </svg>
</div>

<!-- What I Learned -->
<div class="section-card" style="max-width:900px; margin:0 auto 28px;">
  <h2>What I Learned</h2>
  <p>
    이 프로젝트를 통해 CNN 구조가 MLP보다 이미지 분류에 훨씬 적합하다는 점을 실제로 경험할 수 있었다.
    또한 손실 곡선과 정확도 변화를 보면서, “일단 돌려보고 그래프를 해석하는 습관”이
    딥러닝 실험에서 매우 중요하다는 것을 느꼈다.
  </p>
</div>
