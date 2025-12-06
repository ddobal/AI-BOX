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

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Overview</h2>
  <p>
    PlantVillage와 유사한 잎 사진 데이터셋을 이용해,
    잎이 건강한 상태인지 특정 병해에 감염된 상태인지를 분류하는 모델을 구현했다.
    실제 산업 적용 가능성을 염두에 두고, 간단하지만 의미 있는 문제를 선택했다.
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Model & Training</h2>
  <p>
    기본 CNN 모델과 사전 학습된(pretrained) ResNet 계열 모델을 비교해보는 방식으로 진행했다.
    데이터 수가 많지 않은 경우에는 전이학습(transfer learning)이 훨씬 유리하다는 점을 직접 확인할 수 있었다.
  </p>
  <p>
    또한 데이터 증강(augmentation) 기법을 적용했을 때,
    테스트 정확도가 얼마나 안정적으로 변하는지도 실험했다.
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>What I Learned</h2>
  <p>
    현실 세계 이미지는 MNIST처럼 깨끗하지 않아서, 전처리와 데이터 증강의 중요성이 크다는 점을 느꼈다.
    또한, 단순히 정확도만 보는 것이 아니라 클래스별 혼동행렬을 통해
    어떤 클래스에서 실수가 많이 나는지도 함께 분석하는 습관을 갖게 되었다.
  </p>
</div>
