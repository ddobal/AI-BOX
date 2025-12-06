---
layout: default
title: Projects
permalink: /projects/
---

<!-- 📌 미니 히어로 (SVG 로고 적용) -->
<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 로켓 SVG -->
    <svg width="38" height="38" viewBox="0 0 24 24" fill="none">
      <path d="M12 2c2.4 0 4.8.8 6.4 2.4l-4.8 4.8H8L12 2zM4 20l2.4-6.4h4.8l4.8 4.8A10 10 0 0 1 12 22c-2.4 0-4.8-.8-6.4-2.4z"
            fill="url(#rocketGrad)"/>
      <defs>
        <linearGradient id="rocketGrad">
          <stop offset="0%" stop-color="#ff6b6b"/>
          <stop offset="100%" stop-color="#f9d423"/>
        </linearGradient>
      </defs>
    </svg>
  </div>

  <h1>Projects</h1>
  <p class="mini-hero-sub">
    연구 및 개인 개발로 진행한 주요 프로젝트들을 정리합니다.  
    대부분 실제로 빌드하거나 실험한 코드와 구조를 기반으로 하고 있습니다.
  </p>
</div>



<!-- 📌 카드 목록 -->
<div class="section-card-grid--columns">

  <!-- 1 -->
  <section class="section-card">
    <h2 class="section-card-title">AI Vision Automation</h2>
    <p class="section-card-meta">Computer Vision · Automation</p>
    <p>
      실시간 Object Detection + Tracking을 기반으로  
      특정 이벤트 자동 감지 및 로깅을 수행하는 현장 자동화 시스템 구축.
    </p>
  </section>

  <!-- 2 -->
  <section class="section-card">
    <h2 class="section-card-title">Diffusion-based Image Generator</h2>
    <p class="section-card-meta">Generative AI</p>
    <p>
      Stable Diffusion 기반 모델을 커스터마이징하여  
      캐릭터/프로필/컨셉 아트 생성 자동화 파이프라인 제작.
    </p>
  </section>

  <!-- 3 -->
  <section class="section-card">
    <h2 class="section-card-title">RL Trading Bot</h2>
    <p class="section-card-meta">Reinforcement Learning · Trading</p>
    <p>
      강화학습 환경 구축 → 정책 학습 →  
      거래소 API 실거래 연동까지 진행한 트레이딩 에이전트 실험 프로젝트.
    </p>
  </section>

  <!-- 4 -->
  <section class="section-card">
    <h2 class="section-card-title">OCR 기반 문서 자동화 시스템</h2>
    <p class="section-card-meta">OCR · NLP · Automation</p>
    <p>
      문서 스캔 이미지를 OCR로 텍스트 변환 후,  
      필드 자동 분류·정제하여 업무 자동화를 구현한 프로젝트.
    </p>
  </section>

  <!-- 5 -->
  <section class="section-card">
    <h2 class="section-card-title">Realtime Human Pose Tracking</h2>
    <p class="section-card-meta">Pose Estimation · OpenCV</p>
    <p>
      MoveNet 기반 실시간 신체 포즈 분석 시스템.  
      특정 동작 감지 및 자세 분석 기능을 포함.
    </p>
  </section>

  <!-- 6 -->
  <section class="section-card">
    <h2 class="section-card-title">Generative Style Transfer Engine</h2>
    <p class="section-card-meta">Generative AI · Image2Image</p>
    <p>
      다중 스타일 이미지 변환을 위한 Style Transfer 엔진 제작.  
      예술 스타일, 캐릭터 스타일 등 자동 변환.
    </p>
  </section>

  <!-- 7 -->
  <section class="section-card">
    <h2 class="section-card-title">AI 기반 음식 칼로리 추정</h2>
    <p class="section-card-meta">Classification · Computer Vision</p>
    <p>
      음식 이미지로 음식 종류·양을 추정해  
      칼로리를 예측하는 CV 모델 실험.
    </p>
  </section>

  <!-- 8 -->
  <section class="section-card">
    <h2 class="section-card-title">Time-series Anomaly Detection</h2>
    <p class="section-card-meta">Deep Learning · Forecasting</p>
    <p>
      제조·금융 데이터 기반 이상치 탐지를 위한  
      시계열 LSTM/GRU 예측 모델 실험.
    </p>
  </section>

  <!-- 9 -->
  <section class="section-card">
    <h2 class="section-card-title">AI Voice TTS System</h2>
    <p class="section-card-meta">Speech · TTS</p>
    <p>
      Tacotron2 + HiFiGAN 기반 커스텀 음색 TTS 모델.  
      짧은 데이터로 개인 음색 복제 실험.
    </p>
  </section>

  <!-- 10 -->
  <section class="section-card">
    <h2 class="section-card-title">Vision 기반 얼굴 인증 출입 시스템</h2>
    <p class="section-card-meta">Face Recognition · Automation</p>
    <p>
      얼굴 인식 기반 출입 관리 프로토타입 제작.  
      Embedding + Threshold 기반 인증 구조 설계.
    </p>
  </section>

</div>
