---
layout: default
title: Blog
permalink: /blog/
---

<!-- 📌 미니 히어로 (SVG 로고 적용) -->
<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 펜/글쓰기 아이콘 -->
    <svg width="38" height="38" viewBox="0 0 24 24" fill="none">
      <path d="M3 17.25V21h3.75l11-11.03-3.75-3.75L3 17.25zM20.71 7.04c.39-.39.39-1.02 0-1.41l-2.34-2.34a1 1 0 0 0-1.41 0l-1.83 1.83 3.75 3.75 1.83-1.83z"
            fill="url(#blogGrad)" />
      <defs>
        <linearGradient id="blogGrad">
          <stop offset="0%" stop-color="#38f9d7"/>
          <stop offset="100%" stop-color="#4facfe"/>
        </linearGradient>
      </defs>
    </svg>
  </div>

  <h1>Blog</h1>
  <p class="mini-hero-sub">
    AI 실험 과정, 학습 기록, 기술 정리, 그리고 시행착오를 남기는 공간입니다.  
    실제 연구·개발 과정에서 얻은 지식을 꾸준히 문서화하는 것이 목표입니다.
  </p>
</div>


<div class="section-card-grid">

  <!-- 1 -->
  <section class="section-card">
    <h2>📌 Diffusion 모델 구조 정리</h2>
    <p class="section-card-meta">Generative AI · 실험 로그</p>
    <p>
      U-Net 구조부터 Cross-Attention, Scheduler 차이까지  
      Diffusion 모델의 핵심 블록을 정리한 학습 기록.
    </p>
  </section>

  <!-- 2 -->
  <section class="section-card">
    <h2>📌 Object Detection 성능 비교 실험</h2>
    <p class="section-card-meta">Computer Vision · Benchmark</p>
    <p>
      YOLO 계열 모델과 Detector Transformer(DETR)의  
      속도·정확도·추론 비용 비교 실험 결과.
    </p>
  </section>

  <!-- 3 -->
  <section class="section-card">
    <h2>📌 강화학습 환경 설계 포인트</h2>
    <p class="section-card-meta">RL · Trading Bot</p>
    <p>
      관측 공간 설계, 보상 함수 구조,  
      에이전트 안정화를 위한 트릭 등 RL 환경 설계 노트.
    </p>
  </section>

  <!-- 4 -->
  <section class="section-card">
    <h2>📌 이미지 전처리 파이프라인 개선기</h2>
    <p class="section-card-meta">Vision · Data Pipeline</p>
    <p>
      전처리가 모델 성능에 미치는 영향을 실험하고  
      최적 파이프라인을 찾아가는 과정에서의 시행착오 기록.
    </p>
  </section>

  <!-- 5 -->
  <section class="section-card">
    <h2>📌 OpenCV로 만드는 실시간 포즈 시스템</h2>
    <p class="section-card-meta">Pose Estimation · Engineering</p>
    <p>
      MoveNet 기반 실시간 자세 추적기 제작 과정과  
      FPS 최적화 방법 정리.
    </p>
  </section>

  <!-- 6 -->
  <section class="section-card">
    <h2>📌 TTS 음색 복제 실험 로그</h2>
    <p class="section-card-meta">Speech · TTS</p>
    <p>
      Tacotron2 + HiFiGAN 조합으로  
      짧은 음성 데이터로 음색 복제 실험을 진행하며 남긴 기록.
    </p>
  </section>

  <!-- 7 -->
  <section class="section-card">
    <h2>📌 데이터 불균형 문제 해결 전략</h2>
    <p class="section-card-meta">ML · Data Engineering</p>
    <p>
      Oversampling, Class Weight 조정,  
      Augmentation 전략 비교 실험 및 적용 사례.
    </p>
  </section>

  <!-- 8 -->
  <section class="section-card">
    <h2>📌 모델 최적화(Quantization & Pruning) 실험기</h2>
    <p class="section-card-meta">Model Optimization</p>
    <p>
      모델 경량화 과정에서 성능 하락을 최소화하기 위한  
      다양한 전략 실험 결과 공유.
    </p>
  </section>

  <!-- 9 -->
  <section class="section-card">
    <h2>📌 Vision Transformer(ViT) 이해하기</h2>
    <p class="section-card-meta">Deep Learning · Theory</p>
    <p>
      Patch Embedding → Multi-head Attention → Classification Head까지  
      ViT 구조를 단계별로 해석한 학습용 문서.
    </p>
  </section>

  <!-- 10 -->
  <section class="section-card">
    <h2>📌 개인 프로젝트 회고: AI 자동화 시스템 개발</h2>
    <p class="section-card-meta">Project Retrospective</p>
    <p>
      실제 자동화 환경에 AI 모델을 적용하면서 느낀 점,  
      구조 개선 포인트, 향후 계획 등을 정리한 회고 글.
    </p>
  </section>

</div>
