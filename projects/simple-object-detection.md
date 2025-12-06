---
layout: project
title: 간단한 객체 탐지 실습
permalink: /projects/simple-object-detection/
order: 7
---

<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 카메라/박스 아이콘 -->
    <svg viewBox="0 0 24 24" width="32" height="32">
      <rect x="4" y="5" width="16" height="12" rx="2" stroke="#22c55e" stroke-width="1.6" fill="none"/>
      <rect x="9" y="9" width="6" height="4" stroke="#22c55e" stroke-width="1.4" fill="none"/>
    </svg>
  </div>

  <h1>간단한 객체 탐지 실습</h1>
  <p class="mini-hero-sub">
    OpenCV와 기존 모델을 활용해 얼굴·사물 검출을 직접 테스트해 본 컴퓨터비전 입문 프로젝트
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Overview</h2>
  <p>
    이 프로젝트는 복잡한 딥러닝 모델을 직접 학습시키기보다는,
    기존에 공개된 객체 탐지 모델을 활용해 간단한 검출 실험을 해보는 것이 목적이다.
    웹캠 혹은 이미지 파일에서 얼굴이나 특정 사물을 찾아 박스로 표시한다.
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Tools & Methods</h2>
  <p>
    OpenCV에서 제공하는 Haar Cascade 기반 얼굴 검출기를 먼저 사용해 보았고,
    이후에는 사전에 학습된 YOLO 계열 가중치를 불러와 간단히 테스트했다.
  </p>
  <p>
    두 방법의 정확도, 속도, 구현 난이도를 비교하면서
    “라이브러리를 가져다 쓰는 것”과 “직접 학습하는 것”의 차이를 이해하는 데 초점을 두었다.
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>What I Learned</h2>
  <p>
    코드 몇 줄만으로도 꽤 강력한 객체 탐지 결과를 얻을 수 있다는 점이 인상적이었다.
    동시에, 실제 서비스에 적용하려면 데이터셋 구성, 성능 튜닝, 지연 시간 등
    고려할 요소가 훨씬 많다는 것도 느끼게 되었다.
  </p>
</div>
