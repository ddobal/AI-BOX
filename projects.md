---
layout: default
title: Projects
permalink: /projects/
---

<style>
  .section-heading {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 1.1rem;
    margin-bottom: 8px;
  }

  .section-heading-icon {
    width: 24px;
    height: 24px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
  }

  .section-heading-icon svg {
    width: 20px;
    height: 20px;
    display: block;
  }

  /* 이 페이지에서만 그리드 폭 조정 */
  .section-card-grid--columns {
    max-width: 900px; /* 820 → 900 으로 살짝 넓힘 */
    margin: 0 auto 60px;
  }
</style>

<!-- 📌 미니 히어로 (기존 로켓 아이콘 유지) -->
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

  <!-- 공통 프로젝트 아이콘 (격자/보드 느낌) -->
  {% capture project_icon_svg %}
  <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
    <rect x="4" y="4" width="6" height="6" rx="1.2" stroke="white" stroke-width="1.4" />
    <rect x="14" y="4" width="6" height="6" rx="1.2" stroke="white" stroke-width="1.4" />
    <rect x="4" y="14" width="6" height="6" rx="1.2" stroke="white" stroke-width="1.4" />
    <rect x="14" y="14" width="6" height="6" rx="1.2" stroke="white" stroke-width="1.4" />
  </svg>
  {% endcapture %}

  <!-- 1: AI Vision Automation -->
  <a class="section-card section-card-link" href="{{ '/projects/ai-vision-automation/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        {{ project_icon_svg }}
      </span>
      AI Vision Automation
    </h2>
    <p class="section-card-meta">Computer Vision · Automation</p>
    <p>
      실시간 Object Detection + Tracking을 기반으로  
      특정 이벤트 자동 감지 및 로깅을 수행하는 현장 자동화 시스템 구축.
    </p>
  </a>

  <!-- 2: Diffusion-based Image Generator -->
  <a class="section-card section-card-link" href="{{ '/projects/diffusion-image-generator/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        {{ project_icon_svg }}
      </span>
      Diffusion-based Image Generator
    </h2>
    <p class="section-card-meta">Generative AI</p>
    <p>
      Stable Diffusion 기반 모델을 커스터마이징하여  
      캐릭터/프로필/컨셉 아트 생성 자동화 파이프라인 제작.
    </p>
  </a>

  <!-- 3: RL Trading Bot -->
  <a class="section-card section-card-link" href="{{ '/projects/rl-trading-bot/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        {{ project_icon_svg }}
      </span>
      RL Trading Bot
    </h2>
    <p class="section-card-meta">Reinforcement Learning · Trading</p>
    <p>
      강화학습 환경 구축 → 정책 학습 →  
      거래소 API 실거래 연동까지 진행한 트레이딩 에이전트 실험 프로젝트.
    </p>
  </a>

  <!-- 4: OCR 기반 문서 자동화 시스템 -->
  <a class="section-card section-card-link" href="{{ '/projects/ocr-doc-automation/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        {{ project_icon_svg }}
      </span>
      OCR 기반 문서 자동화 시스템
    </h2>
    <p class="section-card-meta">OCR · NLP · Automation</p>
    <p>
      문서 스캔 이미지를 OCR로 텍스트 변환 후,  
      필드 자동 분류·정제하여 업무 자동화를 구현한 프로젝트.
    </p>
  </a>

  <!-- 5: Realtime Human Pose Tracking -->
  <a class="section-card section-card-link" href="{{ '/projects/realtime-human-pose-tracking/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        {{ project_icon_svg }}
      </span>
      Realtime Human Pose Tracking
    </h2>
    <p class="section-card-meta">Pose Estimation · OpenCV</p>
    <p>
      MoveNet 기반 실시간 신체 포즈 분석 시스템.  
      특정 동작 감지 및 자세 분석 기능을 포함.
    </p>
  </a>

  <!-- 6: Generative Style Transfer Engine -->
  <a class="section-card section-card-link" href="{{ '/projects/generative-style-transfer-engine/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        {{ project_icon_svg }}
      </span>
      Generative Style Transfer Engine
    </h2>
    <p class="section-card-meta">Generative AI · Image2Image</p>
    <p>
      다중 스타일 이미지 변환을 위한 Style Transfer 엔진 제작.  
      예술 스타일, 캐릭터 스타일 등 자동 변환.
    </p>
  </a>

  <!-- 7: AI 기반 음식 칼로리 추정 -->
  <a class="section-card section-card-link" href="{{ '/projects/ai-food-calorie-estimation/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        {{ project_icon_svg }}
      </span>
      AI 기반 음식 칼로리 추정
    </h2>
    <p class="section-card-meta">Classification · Computer Vision</p>
    <p>
      음식 이미지로 음식 종류·양을 추정해  
      칼로리를 예측하는 CV 모델 실험.
    </p>
  </a>

  <!-- 8: Time-series Anomaly Detection -->
  <a class="section-card section-card-link" href="{{ '/projects/time-series-anomaly-detection/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        {{ project_icon_svg }}
      </span>
      Time-series Anomaly Detection
    </h2>
    <p class="section-card-meta">Deep Learning · Forecasting</p>
    <p>
      제조·금융 데이터 기반 이상치 탐지를 위한  
      시계열 LSTM/GRU 예측 모델 실험.
    </p>
  </a>

  <!-- 9: AI Voice TTS System -->
  <a class="section-card section-card-link" href="{{ '/projects/ai-voice-tts-system/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        {{ project_icon_svg }}
      </span>
      AI Voice TTS System
    </h2>
    <p class="section-card-meta">Speech · TTS</p>
    <p>
      Tacotron2 + HiFiGAN 기반 커스텀 음색 TTS 모델.  
      짧은 데이터로 개인 음색 복제 실험.
    </p>
  </a>

  <!-- 10: Vision 기반 얼굴 인증 출입 시스템 -->
  <a class="section-card section-card-link" href="{{ '/projects/vision-face-access-control/' | relative_url }}">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        {{ project_icon_svg }}
      </span>
      Vision 기반 얼굴 인증 출입 시스템
    </h2>
    <p class="section-card-meta">Face Recognition · Automation</p>
    <p>
      얼굴 인식 기반 출입 관리 프로토타입 제작.  
      Embedding + Threshold 기반 인증 구조 설계.
    </p>
  </a>

</div>
