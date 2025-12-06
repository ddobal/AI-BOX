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

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
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
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
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
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
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
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>What I Learned</h2>
  <p>
    이 프로젝트를 통해 CNN 구조가 MLP보다 이미지 분류에 훨씬 적합하다는 점을 실제로 경험할 수 있었다.
    또한 손실 곡선과 정확도 변화를 보면서, “일단 돌려보고 그래프를 해석하는 습관”이
    딥러닝 실험에서 매우 중요하다는 것을 느꼈다.
  </p>
</div>
