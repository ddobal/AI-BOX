---
layout: post
title: "이미지 전처리와 데이터 증강이 주는 효과"
date: 2025-04-10
tags: [computer-vision, augmentation, practice]
excerpt: "작은 꽃 이미지 데이터셋에 여러 증강 기법을 적용해 과적합이 줄어드는지, 성능이 실제로 좋아지는지를 확인한 실험."
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
    <path d="M5 19C5 8 12 4 19 5c-1 7-5 14-14 14z" stroke="#22c55e" stroke-width="1.5" fill="none"/>
  </svg>
  <h2>실험 목적</h2>
</div>

<p>
  이미지 분류 성능을 올리기 위해 자주 사용하는 기법이 데이터 증강(augmentation)이다.
  이번 실험에서는 “증강을 하면 정말로 일반화 성능이 좋아지는지”를
  작은 꽃 이미지 데이터셋을 이용해 확인해보는 것이 목표였다.
</p>

<div class="post-section-title">
  <svg viewBox="0 0 24 24" fill="none">
    <rect x="4" y="4" width="16" height="16" rx="2" stroke="#a855f7" stroke-width="1.5"/>
    <path d="M8 9h8M8 13h5" stroke="#a855f7" stroke-width="1.5" stroke-linecap="round"/>
  </svg>
  <h2>실험 구성</h2>
</div>

<p>
  데이터는 클래스 3~4개 수준의 작은 꽃 이미지 세트이고,
  모델은 간단한 CNN 분류기를 사용했다.
</p>
<p>
  비교한 조건은 다음과 같다.
</p>
<ul>
  <li>전처리만 적용 (정규화, 리사이즈)</li>
  <li>전처리 + 수평 뒤집기(horizontal flip)</li>
  <li>전처리 + 랜덤 회전/크롭</li>
</ul>

<div class="post-section-title">
  <svg viewBox="0 0 24 24" fill="none">
    <circle cx="12" cy="12" r="9" stroke="#22c55e" stroke-width="1.5"/>
    <path d="M9 13l2 2 4-5" stroke="#22c55e" stroke-width="1.5" stroke-linecap="round" />
  </svg>
  <h2>결과</h2>
</div>

<p>
  전처리만 했을 때는 train 정확도가 빠르게 올라가지만,
  validation 정확도는 어느 순간부터 더 이상 크게 늘지 않았다.
  수평 뒤집기를 추가하자 validation 정확도가 약간 올라갔고,
  랜덤 회전/크롭까지 적용한 경우에는 과적합이 줄어드는 모습을 볼 수 있었다.
</p>
<p>
  다만, 회전 각도를 너무 크게 잡는 등 과한 증강을 적용했을 때는
  오히려 성능이 떨어지는 경우도 있었다.
</p>

<div class="post-section-title">
  <svg viewBox="0 0 24 24" fill="none">
    <rect x="5" y="4" width="14" height="16" rx="2" stroke="#e5e7eb" stroke-width="1.4"/>
    <path d="M8 9h8M8 13h6" stroke="#e5e7eb" stroke-width="1.4" stroke-linecap="round"/>
  </svg>
  <h2>느낀 점</h2>
</div>

<p>
  데이터 증강은 “많이 할수록 무조건 좋은 것”이 아니라,
  실제 데이터 특성에 맞게 적절하게 넣어야 한다는 걸 느꼈다.
  현실 이미지 문제를 다룰수록,
  전처리와 증강이 모델 구조만큼이나 중요하다는 것도 점점 더 느껴지는 중이다.
</p>
