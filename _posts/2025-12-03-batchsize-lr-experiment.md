---
layout: post
title: "배치 크기와 학습률에 따른 학습 곡선 비교"
date: 2025-04-02
tags: [deep-learning, optimization, practice]
excerpt: "배치 크기와 학습률 조합을 바꿔가며 CNN 학습 곡선을 비교하고, 어떤 설정이 안정적으로 학습되는지 관찰한 실험."
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
    <path d="M5 16l4-3 4 2 6-7" stroke="#38bdf8" stroke-width="1.6" fill="none"/>
  </svg>
  <h2>실험 목적</h2>
</div>

<p>
  딥러닝 실습마다 항상 등장하는 하이퍼파라미터가 배치 크기(batch size)와
  학습률(learning rate)이다. 이번에는 이 두 값을 직접 바꿔 보면서
  손실 곡선과 최종 성능이 어떻게 달라지는지 관찰하는 데 집중했다.
</p>

<div class="post-section-title">
  <svg viewBox="0 0 24 24" fill="none">
    <rect x="4" y="4" width="16" height="16" rx="2" stroke="#a855f7" stroke-width="1.5"/>
    <path d="M8 10h8M8 14h5" stroke="#a855f7" stroke-width="1.5" stroke-linecap="round"/>
  </svg>
  <h2>실험 설정</h2>
</div>

<p>
  데이터는 CIFAR-10 중 일부 클래스만 사용한 소규모 이미지 분류 셋이고,
  모델은 작은 CNN(Conv → ReLU → Pool × 2 + Dense)을 사용했다.
</p>
<p>
  비교한 설정은 다음과 같다.
</p>
<ul>
  <li>Batch size: 16, 64, 256</li>
  <li>Learning rate: 0.001, 0.01</li>
</ul>
<p>
  각 조합마다 약 20 epoch 정도 학습시키고, epoch별 train/validation loss를 기록했다.
</p>

<div class="post-section-title">
  <svg viewBox="0 0 24 24" fill="none">
    <circle cx="12" cy="12" r="9" stroke="#22c55e" stroke-width="1.5"/>
    <path d="M8 12h8M12 8v8" stroke="#22c55e" stroke-width="1.5" stroke-linecap="round"/>
  </svg>
  <h2>결과 및 관찰</h2>
</div>

<p>
  작은 배치(16)는 손실 곡선이 조금 요동치는 느낌이었지만,
  최종 성능은 나쁘지 않았다. 큰 배치(256)는 학습이 안정적으로 보이지만,
  같은 epoch 수 기준으로 손실이 충분히 떨어지지 않는 경우도 있었다.
</p>
<p>
  학습률 0.01은 일부 조합에서 손실이 발산하거나 불안정하게 움직였고,
  0.001이 전체적으로 더 안정적인 결과를 보여줬다.
</p>

<div class="post-section-title">
  <svg viewBox="0 0 24 24" fill="none">
    <rect x="5" y="4" width="14" height="16" rx="2" stroke="#e5e7eb" stroke-width="1.4"/>
    <path d="M8 9h8M8 13h6" stroke="#e5e7eb" stroke-width="1.4" stroke-linecap="round"/>
  </svg>
  <h2>느낀 점</h2>
</div>

<p>
  하이퍼파라미터에는 정답이 있는 게 아니라,
  데이터와 모델에 따라 괜찮은 구간을 찾는 과정이라는 걸 다시 느꼈다.
  앞으로는 배치와 학습률을 한 번에 고정하기보다는,
  여러 조합을 짧게 테스트해보는 습관을 들이면 좋겠다는 생각이 들었다.
</p>
